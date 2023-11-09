<template>
    <div class="window">
        <div class="sidebar-container">
            <side-bar/>
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
import SideBar from './SideBar'
export default{
    components:{
      SideBar,
    },
}
</script>

<style>
    .window{
        height:100%;
        width:100%;
        display:flex;
        flex-flow:row nowrap;
        align-items: center;
        position:relative;
    }
    .sidebar-container{
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
        align-content: flex-start;
    }
    .path{
        height: 50px;
        width:100%;
        background-color: rgba(75, 186, 223, 0.295);
    }
</style>