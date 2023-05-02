<template>
    <div class="icon-container" >
        <slot>
            <span>
                {{symbole}}
            </span>
        </slot>
    </div>
</template>
<script>
export default {
    inject:[
        'symbole',
    ]
}
</script>
<style scoped>
    .icon-container{
        height: 30px;
        width:30px;
        border-radius: 50%;
        color:white;
        font-size:16px;
        background-color: rgb(1, 156, 71);
        display:flex;
        align-items:center;
        justify-content: center;
        margin-right: 5px;
    }
    .sidebar-item:hover > .icon-container{
         background-color: rgb(3, 116, 27);
    }
</style>