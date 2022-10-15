<template>
    <form>
        <form-title text='Login Form'/>
        <form-input type='text' placeholder='firstname, E.g: John' v-model="fname"/>
        <form-input type='text' placeholder='lastname, E.g: DOE' v-model="lname"/>
        <form-submit-button @checkUser="$emit('checkUser', inputData)"  text="Change the name" />
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
            fname: "",
            lname: "",
        }
    },
    watch :{
        fname(newValue, oldValue){
            if(newValue != oldValue){
                this.fname=newValue
            }
        },
        lname(newValue, oldValue){
            if(newValue != oldValue){
                this.lname=newValue
            }
        }
    },
    computed:{
        inputData(){
            return [this.fname, this.lname]
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
</style>
