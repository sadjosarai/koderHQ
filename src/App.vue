<template>
  <template v-if="!log">
    <component  @checkUser="checkUser" @addUser = "addUser" :is="formName"/>
    <div class="where-are-you">
      <p @click="switching">
        {{message}}
      </p>
    </div>
  </template>
  <template v-if="statusChecked">
    <div v-if="render == 'administrator'">
      <p class="good">Welcome, administrator </p>
      <user-home>
        <img class="card-img" src="data:image/jpeg;base64,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"/>
        <div class="card-title">
          <p>
            {{fullname}}
          </p>
        </div>
      </user-home>
    </div>
    <div v-else-if="render=='user'">
      <p class="good">Welcome, user {{fullname}}</p>
      <user-home>
        <img src="data:image/jpeg;base64,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"/>
      </user-home>
    </div>
    <div v-else>
      <p class=warning>you are not registered in our data base</p>
    </div>
  </template>
</template>

<script>
  import LoginForm from './components/LoginForm'
  import UserHome from './components/UserHome'
  import SignUpForm from './components/SignUpForm'
  export default {
    name: 'App',
    components:{
      LoginForm,
      UserHome,
      SignUpForm
    },
    data(){
      return{
        user:[
          {
            firstname:"john",
            lastname :"DOE",
            username : 'john',
            password: 'DOE',
            right :"user",
          },
          {
            firstname:"jane",
            lastname :"DOE",
            username : 'jane',
            password: 'DOE',
            right :"administrator",
          }
        ],
        firstname: "",
        lastname: "",
        fullname: "",
        render:"",
        formName : 'login-form',
        statusChecked  : false,
        message : 'not yet registered? click here!',
        newData : '' ,
        log : false  
      }
    },
    methods:{
      checkUser(data){
        this.username = data[0];
        this.password = data[1];
        this.statusChecked = true;
        for(let u of this.user){
          if((u.username == this.username) && (u.password == this.password)){
            this.fullname = u.firstname + ' ' + u.lastname;
            this.log = true;
            this.render = u.right;
          }
        }
      },
      switching(){
        if(this.formName == 'login-form'){
          this.formName = 'sign-up-form'
          this.message = 'already registered? click here!';
        }else{
          this.formName= 'login-form'
          this.message = 'not yet registered? click here!';
        }
      },
      addUser(data){
        this.newData = data;
        let newUser = {
          firstname : data[0],
          lastname : data[1],
          dateOfBirth : data[2],
          placeOfBirth : data[3],
          username : data[4],
          password : data[5],
          right: 'user'
        }
        this.user.push(newUser);
        this.statusChecked = false;
        this.formName = 'login-form';
      }
    },
    watch:{
      user(newValue, oldValue){
        if(newValue != oldValue){
          this.user = newValue;
        }
      },
    
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
  .card-img{
    position:absolute;
    top:0;
    width:100%;
    height: 60%;
    display:block;
  }
  .card-title{
    display:block;
    max-height: 100px;
    width:100%;
    display:flex;
    flex-flow:column wrap;
    justify-content: center;
    align-items:center;
    position:relative;
  }
  .where-are-you{
    margin-top: 20px;
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
    font-size:16px;
  }
  .where-are-you:hover{
    cursor: pointer;
    color:rgb(28, 107, 224);
  }
</style>
