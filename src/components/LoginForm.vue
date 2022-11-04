<template>
    <form>
        <form-title text='Login Form'/>
        <form-input type='text' placeholder='username' v-model="username" ref="usernameRef" />
        <form-input type='password' placeholder='Password' v-model="password" ref="passwordRef"/>
        <form-submit-button @checkUser="$emit('checkUser', inputData)"  text="Sign In" />
    </form>
</template>
<script>
import FormInput from './FormInput'
import FormTitle from './FormTitle'
import FormSubmitButton from './FormSubmitButton'
export default {
    components:{
        FormInput,
        FormSubmitButton,
        FormTitle
    },
    emits:[
        'checkUser',
    ],
    data(){
        return {
            username: "",
            password: "",
        }
    },
    watch :{
        username(newValue, oldValue){
            if(newValue != oldValue){
                this.username=newValue
            }
        },
        password(newValue, oldValue){
            if(newValue != oldValue){
                this.password=newValue
            }
        }
    },
    computed:{
        inputData(){
            return [this.username, this.password]
        }
    },
    mounted(){
        this.focusInput()
    },
    methods:{
        focusInput(){
            this.$refs.usernameRef.focus()
        }
    }
}
</script>
<style scoped>
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
    button{
        position:absolute;
        bottom:50px;
    }

</style>
