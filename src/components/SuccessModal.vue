<template>
    <div class="modal">
        <div class="close">
            <button @click="$emit('closeModal')">X</button>
        </div>
        <div class="modal-content">
            <p style="text-align:center;">
                <span style="color:green;font-size:48px">Welcome</span>{{fullname}}
            </p>
        </div>
    </div>
</template>
<script>
export default {
    emits:[
        'closeModal'
    ],
    inject :[
        'fullname'
    ],
}
</script>
<style scoped>
    .close{
        height:20%;
        width:100%;
        display:flex;
        padding-right:15px;
        padding-top:15px;
        justify-content: flex-end;
    }
    .modal-content{
        height:80%;
        width:100%;
        display:flex;
        justify-content: center;
        align-items:center;
    }
    .modal{
        width:500px;
        height: 350px;
        background-color:white;
        backdrop-filter: blur(60%);
        border-radius: 5px 5px;
        display:flex;
        flex-direction:column;
        align-items: center;
        justify-content: center;
    }
    button{
        height:25px;
        width: 25px;
        color:white;
        background-color: rgb(9, 69, 99);
        outline: 1px solid rgb(96, 138, 230);
        border-radius:50%;
    }
    button:hover{
        background-color:rgb(190, 20, 20);
        outline: 1px solid rgb(219, 77, 77);
    }
</style>