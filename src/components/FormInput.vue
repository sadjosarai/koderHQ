<template>
    <input :type="type"/>
</template>
<script>
export default {
    data(){
        return {
            type: "text"
        }
    }
}
</script>
<style scoped>
    input{
        outline:none;
        border-radius:5px;
        border:1px solid grey;
        height:30px;
        width:80%;
        margin: 10px auto;
        }
</style>