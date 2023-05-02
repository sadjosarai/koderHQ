<template>
    <div 
    class="sidebar-item" 
    :text="text"
    :symbole="symbole"
    >
        <SideBarButton/>
        <p>
            {{text}}
        </p>
        <!-- <slot v-if="options">

        </slot> -->
    </div>
</template>
<script>
import SideBarButton from './SideBarButton';
export default {
    components:{
        SideBarButton,
    },
    props:[
        'text',
        'symbole'
    ],
    data(){
        return{
           options:false, 
        }
    },
    provide(){
        return{
            symbole : this.symbole
        }
    }
}
</script>
<style scoped>
 .sidebar-item{
    margin-top: 5px;
    display: flex;
    width:90%;
    flex-direction: row;
    color:white;
    align-items: center;
    justify-content: flex-start;
    padding:5px;
    background-color: rgba(255, 255, 255, 0.15);
    backdrop-filter: blur(2px);
    text-align: left;
 }
 .sidebar-item:hover{
    background-color: rgba(255, 255, 255, 0.40);
    backdrop-filter: blur(6px);
    box-shadow: 0px 2px 2px 1px rgba(128, 128, 128, 0.5);
    cursor: pointer;
 }
</style>