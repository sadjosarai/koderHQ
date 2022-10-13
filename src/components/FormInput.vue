<template>
    <input :type="type" :placeholder='placeholder'/>
</template>
<script>
export default {
    props:[
        'type',
        'placeholder',
    ],
    data(){
        return {
        }
    }
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
</style>