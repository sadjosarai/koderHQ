<template>
    <form>
        <form-title text='Step 1'/>
        <form-input type='text' placeholder='firstname, E.g: John' v-model="fName" required/>
        <form-input type='text' placeholder='lastname, E.g: DOE' v-model="lName"/>
        <form-input type='date' placeholder='Date of birth, E.g: 01/01/2000' v-model="dBirth" required/>
        <form-input type='text' placeholder='Place of birth, E.g: Yaounde' v-model="pBirth" required/>
        <form-submit-button @click="$emit('step', inputData)"  text="Next Step" />
    </form>
</template>
<script>
    import FormInput from './FormInput'
    import FormTitle from './FormTitle'
    import FormSubmitButton from './FormSubmitButton'
    export default {
        components: {
            FormInput,
            FormTitle,
            FormSubmitButton
        },
        emits :[
            'step'
        ],
        data(){
            return {
                fName: '',
                lName: '',
                dBirth: '',
                pBirth: '',
                step : 'step-1',
            }
        },
        watch: {
            fName(newValue, oldValue){
                if(newValue != oldValue){
                    this.fName = newValue;
                }
            },
            lName(newValue, oldValue){
                if(newValue != oldValue){
                    this.lName = newValue;
                }
            },
            dBirth(newValue, oldValue){
                if(newValue != oldValue){
                    this.dBirth = newValue;
                }
            },
            pBirth(newValue, oldValue){
                if(newValue != oldValue){
                    this.pBirth = newValue;
                }
            }
        },
        computed : {
            inputData(){
                return [this.fName, this.lName, this.dBirth, this.pBirth, this.step]
            }
        }
    }
</script>
<style scoped>
    form{
        border-radius:5px;
        width:300px;
        height:450px;
        border:1px solid grey;
        padding:15px 0px;
        display:flex;
        flex-direction:column;
        align-items: center;
        position : relative;
    }
</style>