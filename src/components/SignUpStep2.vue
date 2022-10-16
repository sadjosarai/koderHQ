<template>
    <form>
        <form-title text='Step 2'/>
        <p v-if="error">
            {{error}}
        </p>
        <form-input type='text' placeholder='enter your username' v-model="username" required/>
        <form-input type='password' placeholder='enter your password' v-model="password" required/>
        <form-input type='password' placeholder='confirm your password' v-model="cPassword" required/>
        <div class="button-div">
            <form-submit-button @click="$emit('Step', inputData)"  text="Previous Step" />
            <form-submit-button @click="checkPassword"  text="Submit" />
        </div>
    </form>
</template>
<script>
    import FormInput from './FormInput'
    import FormTitle from './FormTitle'
    import FormSubmitButton from './FormSubmitButton'
    export default {
        components: [
            FormInput,
            FormTitle,
            FormSubmitButton
        ],
        emits :[
            'Step',
        ],
        data(){
            return {
                userName: '',
                password: '',
                cPassword: '',
                pBirth: '',
                step : 'step-2',
                error : '',
            }
        },
        methods:{
            checkPassword(){
                if(this. username && this.password && this.cPassword){
                    if(this.password == this.cPassword){
                        this.step = 'ready';
                        this.$emit('Step', this.inputData);
                    }else{
                        this.error = 'the two password must be similar';
                    }
                }else{
                    this.error = 'please fill all the field';
                }
            }
        },
        watch: {
            username(newValue, oldValue){
                if(newValue != oldValue){
                    this.username = newValue;
                }
            },
            password(newValue, oldValue){
                if(newValue != oldValue){
                    this.password = newValue;
                }
            },
            cPassword(newValue, oldValue){
                if(newValue != oldValue){
                    this.cPassword = newValue;
                }
            },
        },
        computed : {
            inputData(){
                return [this.username, this.password, this.step]
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
    .button-div{
        width :90%;
        display: flex;
        flex-flow: row nowrap;
    }
    form-submit-button{
        width: 45%;
    }
</style>