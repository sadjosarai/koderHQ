<template>
  <form>
    <label>
      first name : 
    </label>
    <input type="text" v-model="firstname"/> <br/>
    <label>
      last name : 
    </label>
    <input type="text" v-model="lastname"/>
    <br/>
    <button @click.prevent="checkUser">change the name</button>
  </form>
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
      firstname: "john",
      lastname: "connor",
      fullname: "",
      render:"",
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
      for(let u of this.user){
        if((u.firstname == this.firstname) && (u.lastname == this.lastname)){
          this.render = u.right;
        }
      }
    }
  }
}
</script>

<style scoped>
 form{
  width:300px;
  height:250px;
  border:1px solid grey;
  box-shadow: 1px 1px 2px 2px black;
  margin: 0 auto;
  padding:15px 0px;
 }
 input{
  outline:none;
  border:1px solid grey;
  height:20px;
  width:150px;
 }
</style>
