<template>
    <div class="icon-container">
        <slot>
            <span>
                +
            </span>
        </slot>
    </div>
</template>
<script>
export default {
    
}
</script>
<style>
    .icon-container{
        height: 80px;
        width:50px;
        border-radius: 5px;
        color:white;
        font-size:36px;
        background-color: rgb(1, 156, 71);
    }
    .icon-container:hover{
        background-color: rgb(3, 116, 27);
    }
</style>