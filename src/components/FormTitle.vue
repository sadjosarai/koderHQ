<template>
    <h2 class='form-title-2'> {{text}} </h2>
</template>
<script >
    export default{
        props:[
            'text'
        ]
    }
</script>
<style>
    .form-title-2{
        font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
        font-size:36px;
        color:rgb(28, 107, 224);
    }
</style>