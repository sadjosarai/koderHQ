<template>
  <login-form @checkUser="checkUser" v-if='!registered'/>
  <template v-if="statusChecked">
    <div v-if="render=='administrator'">
      <p class="good">Welcome, administrator {{fullname}}</p>
    </div>
    <div v-else-if="render=='user'">
      <p class="good">Welcome, user {{fullname}}</p>
    </div>
    <div v-else>
      <p class=warning>you are not registered in our data base</p>
    </div>
  </template>
</template>

<script>
  import LoginForm from './components/LoginForm'
  export default {
    name: 'App',
    components:{
      LoginForm,
    },
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
        registered: false,
        statusChecked  : false
      }
    },
    methods:{
      checkUser(data){
        this.firstname = data[0];
        this.lastname = data[1];
        this.fullname = this.firstname + ' ' + this.lastname;
        this.statusChecked = true;
        for(let u of this.user){
          if((u.firstname == this.firstname) && (u.lastname == this.lastname)){
            this.registered = !this.registered;
            this.render = u.right;
          }
        }
      }
    },
    watch:{
      fullname(newValue, oldValue){
        if(newValue!=oldValue){
          alert('you changed your name to this : ' + this.fullname)
        }
      }
    },
  }
</script>

<style>
  p{
    text-align:center;
    vertical-align:center;
    margin: 0 auto;
  }
  .good{
    color:green;
  }
  .warning{
    color:red;
    margin-top:20px;
  }
</style>
