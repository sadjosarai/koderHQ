<template>
  <login-form />
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
  <greeting-message/>
</template>

<script>
  import GreetingMessage from './components/GreetingMessage'
  import LoginForm from './components/LoginForm'
  export default {
    name: 'App',
    components:{
      GreetingMessage,
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
 
</style>
