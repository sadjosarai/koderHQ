<template>
    <div class="sidebar">
        <div class="new-item">
            <div class="icon-container">
                <span>
                    +
                </span>
            </div>
            <slot>
                Add whatever
            </slot>
        </div>
        <sideBarItem companyOrProjectName="company 1" companyLogo="./assets/logo1"/>
    </div>
</template>
<script>
import SideBarItem from './SideBarItem'
export default {
    components:{
        SideBarItem,
    }
    
}
</script>
<style>
.sidebar{
    width : 100%;
    height :100%;
    margin: 15px;
    display:flex;
    flex-flow:column nowrap;
    gap : 10px;
    justify-content: flex-start;
    align-items: center;
}
.icon-container{
    height: 40px;
    width:40px;
    border-radius: 5px;
    color:white;
    font-size:36px;
    background-color: rgb(1, 156, 71);
    display:flex;
    align-items:center;
    justify-content: center;
}
.icon-container:hover{
    background-color: rgb(3, 116, 27);
}
.new-item{
    display: flex;
    gap:10px;
    flex-flow: row nowrap;
    align-items: center;
    justify-content: flex-start;
    padding : 2px 5px;
    background-color: rgba(225, 30, 243, 0.781);
    width:90%;
    height: 50px; 
    box-shadow: 1px 1px 1px 2px rgba(0, 0, 0, 0.5);
    font-size: 1.2em;
}
.new-item:hover{
    background-color: rgba(122, 26, 131, 0.897);;
}
</style>