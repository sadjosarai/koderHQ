<template>
  <form v-if="registered">
    <h2 class='form-title-2'> Form </h2>
    <input type="text" v-model="firstname" placeholder="firstname, E.g: John"/>
    <br/>
    <input type="text" v-model="lastname" placeholder="lastname, E.g: DOE"/>
    <br/>
    <button @click.prevent="checkUser">change the name</button>
  </form>
  <template v-if="statuschecked">
    <div v-if="render=='administrator'">
      <p>Welcome, administrator {{fullname}}</p>
    </div>
    <div v-else-if="render=='user'">
      <p>Welcome, user {{fullname}}</p>
    </div>
    <div v-else>
      <p>you are not registered in our data base</p>
    </div>
  </template>
</template>

<script>
export default {
  name: 'App',
  data(){
    return{
      user:[
        {
          firstname:"john",
          lastname :"DOE",
          right :"user",
        },
        {
          firstname:"jane",
          lastname :"DOE",
          right :"administrator",
        }
      ],
      firstname: "",
      lastname: "",
      fullname: "",
      render:"",
      registered: true,
      statuschecked  : false
    }
  },
  watch:{
    fullname(newValue, oldValue){
      if(newValue!=oldValue){
        alert('you changed your name to this : ' + this.fullname)
      }
    }
  },
  methods:{
    checkUser(){
      this.fullname = this.firstname + ' ' + this.lastname;
      this.statuschecked = true;
      for(let u of this.user){
        if((u.firstname == this.firstname) && (u.lastname == this.lastname)){
          this.registered = false;
          this.render = u.right;
        }
      }
    }
  }
}
</script>

<style>
 #app{
  display:flex;
  flex-direction:column;
  align-items: center;
  justify-content:center;
 } 
 form{
  border-radius:5px;
  width:300px;
  height:350px;
  border:1px solid grey;
  padding:15px 0px;
  display:flex;
  flex-direction:column;
  align-items: center;
  position : relative;
 }
 input{
  outline:none;
  border-radius:5px;
  border:1px solid grey;
  height:30px;
  width:80%;
  margin: 10px auto;
 }
 button{
  background-color:rgb(8, 145, 8);
  color:white;
  border:none;
  border-radius:5px;
  position:absolute;
  width:80%;
  height:30px;
  bottom:50px;
 }
 button:hover{
  background-color:rgb(4, 119, 4);
  cursor:pointer;
 }
 .form-title-2{
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
  font-size:36px;
  color:rgb(28, 107, 224);
 }
</style>
