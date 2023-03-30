<template>
    <div class="window">
        <div class="sideBar">
            <side-bar-item text="New Company"/>
            <side-bar-item text="company name 2"/>
            <side-bar-item text="company name 3"/>
            <side-bar-item text="company name 4"/>
            <side-bar-item text="company name 5"/>
        </div>
        <div class="workspace">
            <nav class="path">

            </nav>
            <div class="contents">

            </div>
        </div>
    </div>
</template>
<script>
import SideBarItem from './SideBarItem'
export default{
    components:{
      SideBarItem,
    },
}
</script>

<style scoped>
    .window{
        height:90%;
        width:100%;
        display:flex;
        flex-flow:row nowrap;
        align-items: center;
        position:relative;
    }
    .sideBar{
        padding-top:0px;
        width:20%;
        height:100%;
        background-image: linear-gradient(rgb(75, 186, 223),rgb(100, 98, 240), rgb(75, 186, 223),rgb(75, 186, 223));
        display:flex;
        flex-flow:column nowrap;
        justify-content: flex-start;
        align-items:center;
    }
    .workspace{
        width:80%;
        height:100%;
        background-color: white;
        display:flex;
        flex-flow: column nowrap;
        justify-content:flex-start;
        align-content: center;
    }
    .path{
        height: 50px;
        width:100%;
        background-color: rgba(75, 186, 223, 0.295);
    }
</style>