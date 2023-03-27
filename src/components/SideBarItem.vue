<template>
    <div 
    class="sidebar-item" 
    :text="text"
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
    ],
    data(){
        return{
           options:false, 
        }
    }
}
</script>
<style scoped>
 .sidebar-item{
    margin-top: 5px;
    display: flex;
    flex-direction: row;
    color:white;
    align-items: center;
    justify-content: flex-start;
    padding:5px;
 }
</style>