<template>
    <input 
        :type="type" 
        :placeholder='placeholder' 
        :value="modelValue"
        @input="$emit('update:modelValue', $event.target.value)"
        ref="inputRef"
    />
</template>
<script>
export default {
    props:{
        type :{
            type : String,
            required: true,
            default: 'text'
        },
        placeholder : {
            type : String,
            required : false,
            default : 'write here...'
        },
        modelValue : {
            type : String,
            required : false,
            default : ""
        }
    },
    data(){
        return {

        }
    },
    methods:{
        focus(){
            this.$refs.inputRef.focus()
        }
    },
    // mounted(){
    //     this.focus()
    // }
}
</script>
<style scoped>
    input{
        outline:none;
        border-radius:5px;
        border:1px solid rgb(160, 160, 160);
        height:30px;
        width:70%;
        margin: 10px auto;
        padding : 0 15px;
        }
    input:focus{
        outline: 1px solid rgb(86, 86, 240);
        background-color: rgb(177, 185, 221);
    }
</style>