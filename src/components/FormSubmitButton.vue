<template>
    <button @click.prevent="$emit('checkUser')">{{text}}</button>
</template>
<script>
    export default{
        props:{
            text: {
                type : String,
                required : true,
                default : 'Submit'
            }
        },
        emits : [
            'checkUser'
        ]
    }
</script>
<style scoped>
    button{
        background-color:rgb(8, 145, 8);
        color:white;
        border:none;
        border-radius:5px;
        position:absolute;
        width:80%;
        height:30px;
        bottom:50px;
    }
    button:hover{
        background-color:rgb(4, 119, 4);
        cursor:pointer;
    }
</style>
