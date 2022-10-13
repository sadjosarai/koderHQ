<template>
    <form>
        <!--
        <input type="text" v-model="firstname" placeholder="firstname, E.g: John"/>
        <br/>
        <input type="text" v-model="lastname" placeholder="lastname, E.g: DOE"/>
        <br/>
        <button @click.prevent="checkUser">change the name</button>
        -->
        <form-title/>
        <form-input />
        <form-input />
        <form-submit-button />
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
    data(){
        return {

        }
    },
    
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
