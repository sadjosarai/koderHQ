<template>
    <div 
    class="sidebar-item" 
    :text="text"
    :symbole="symbole"
    :type='type'
    >
        <!-- <SideBarButton/> -->
        <component :is="componentName"/>
        <p>
            {{text}}
        </p>
        <!-- <slot v-if="options">

        </slot> -->
    </div>
</template>
<script>
import SideBarButton from './SideBarButton';
import SideBarListButton from './SideBarListButton';
export default {
    components:{
        SideBarButton,
        SideBarListButton,
    },
    props:[
        'text',
        'symbole',
        'type'
    ],
    data(){
        return{
           options:false, 
        }
    },
    computed:{
        componentName() {
            if(this.$props.type == 'b'){
                return 'side-bar-list-button'
            }else{
                return 'side-bar-button'
            }
        }
    },
    created(){
        console.log(this.$props.type)
    },
    provide(){
        return{
            symbole : this.symbole
        }
    },
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
    cursor: pointer;
 }
</style>