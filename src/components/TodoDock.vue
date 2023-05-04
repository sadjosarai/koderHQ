<template>
    <div class="dock-container"
        :type="type"
    >
        <div class="dock-header">
            <div class="dock-title">TODO{{type}}</div>
            <div class="dock-option">...</div>
        </div>
        <div class="dock-body">
            <slot>
                no card...
            </slot>
        </div>
    </div>

</template>
<script>
export default {
    props:[
        'type',
    ]
}
</script>
<style scoped>
    .dock-container{
        background-color: rgb(202, 192, 179);
        width:250px;
        height: auto;
        max-height: 90vh;
        display: flex;
        flex-direction: column;
        justify-content: start;
        align-items: center;
        border-radius:10px 10px 0px 0px;
        padding-bottom:10px;
    }
    .dock-container:hover{
        background-color: rgb(200, 190, 180);;
        color:black;
        box-shadow: 0px 0px 1px 1px rgba(128, 128, 128, 0.445);
    }
    .dock-header{
        display: flex;
        flex-direction: row;
        padding:0px 10px;
        justify-content: space-between;
        align-items: center;
        width:90%;
    }
    .dock-title{
        font-weight: bold;
        font-size:20px;
        color:rgb(80, 80, 80);
        width: fit-content;
    }
    .dock-option{
        font-weight: bold;
        font-size:22px;
        color:rgb(128, 128, 128);
        width: fit-content;
        vertical-align: middle;
    }
    .dock-option:hover{
        color:rgb(44, 44, 44);
        cursor: pointer;
    }
    .dock-body{
        width:calc(95% - 20px);
        background-color: beige;
        color:grey;
        padding:0px 10px;
    }
</style>