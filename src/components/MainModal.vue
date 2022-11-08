<template>
    <div class="main-modal-container">
        <success-modal @closeModal="$emit('closeModal')"/>
    </div>
</template>
<script>
import SuccessModal from './SuccessModal';
export default {
    components:{
        SuccessModal
    },
    data(){
        return{

        }
    }
}
</script>
<style>
    .main-modal-container{
        background-color:rgba(200, 220, 250, 0.664);
        -webkit-backdrop-filter: blur(5px);
        backdrop-filter: blur(5px);
        width:100vw;
        height:100vh;
        display:flex;
        justify-content:center;
        align-items:center;
    }
</style>