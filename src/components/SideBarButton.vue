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
        height: 30px;
        width:30px;
        border-radius: 5px;
        color:white;
        font-size:36px;
        background-color: rgb(1, 156, 71);
        display:flex;
        align-items:center;
        justify-content: center;
        margin-right: 5px;
    }
    .icon-container:hover{
        background-color: rgb(3, 116, 27);
    }
</style>