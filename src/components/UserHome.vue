<template>
    <div class="window">
<<<<<<< HEAD
        <div class="sideBar">
            <side-bar-item text="New Company" symbole="+" type='l'/>
            <side-bar-item text="company name 2" symbole="C" type="b"/>
            <side-bar-item text="company name 3" symbole="C" type="b"/>
            <side-bar-item text="company name 4" symbole="C" type="b"/>
            <side-bar-item text="company name 5" symbole="C" type="b"/>
        </div>
        <div class="workspace">
            <nav class="path">
                <a href="">home</a>
                 > 
                <a href="">Company name</a> 
                 > 
                <a href="">Project name</a>
            </nav>
            <div class="contents">
                <todo-dock/>
=======
        <div class="sidebar-container">
            <side-bar/>
        </div>
        <div class="workspace">
            <nav class="path">

            </nav>
            <div class="contents">

>>>>>>> 246a1d7bc46cdead46eea6839b44d97ec485531b
            </div>
        </div>
    </div>
</template>
<script>
<<<<<<< HEAD
import SideBarItem from './SideBarItem'
import TodoDock from './TodoDock'
export default{
    components:{
      SideBarItem,
      TodoDock
=======
import SideBar from './SideBar'
export default{
    components:{
      SideBar,
>>>>>>> 246a1d7bc46cdead46eea6839b44d97ec485531b
    },
}
</script>

<<<<<<< HEAD
<style scoped>
    .window{
        height:90%;
=======
<style>
    .window{
        height:100%;
>>>>>>> 246a1d7bc46cdead46eea6839b44d97ec485531b
        width:100%;
        display:flex;
        flex-flow:row nowrap;
        align-items: center;
        position:relative;
    }
<<<<<<< HEAD
    .sideBar{
        padding-top:0px;
=======
    .sidebar-container{
>>>>>>> 246a1d7bc46cdead46eea6839b44d97ec485531b
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
<<<<<<< HEAD
        align-content: center;
    }
    .path{
        height: 50px;
        width: calc(100% - 10px);
        background-color: rgba(75, 186, 223, 0.295);
        color:white;
        font-size:18px;
        display: flex;
        align-items: center ;
        padding-left: 10px;
    }
    .path a{
        text-decoration: none;
        color:white;
        margin:0 5px;
        padding-bottom: 4px;
    }
    .path a:hover{
        color : rgb(100, 98, 240);
    }
    .contents{
        padding: 10px 20px;
        width:calc(100%-40px);
        display: flex;
        flex-flow:row nowrap;
        justify-content: flex-start;
=======
        align-content: flex-start;
    }
    .path{
        height: 50px;
        width:100%;
        background-color: rgba(75, 186, 223, 0.295);
>>>>>>> 246a1d7bc46cdead46eea6839b44d97ec485531b
    }
</style>