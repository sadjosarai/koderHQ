<template>
    <div class="user-header">
       <slot id="logo">

       </slot>
       <slot id="navigation">

       </slot>
       <slot id="user-profile">

       </slot>
    </div>
</template>
<script>
export default {
    
}
</script>
<style scope>
    .user-header{
        height:70px;
        width:100vw;
        /* background-image: linear-gradient(to right rgb(70, 68, 190), rgb(75, 186, 223), rgb(75, 186, 223), rgb(75, 186, 223), rgb(70, 68, 190)); */
        background-color: rgba(140, 67, 209, 0.808);
        display :flex;
        justify-content: space-between;
        position:relative;
    }
</style>