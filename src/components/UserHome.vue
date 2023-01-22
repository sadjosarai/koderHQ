<template>
    <div class="window">
        <div class="sideBar">

        </div>
        <div class="workspace">
            <nav class="path">

            </nav>
            <div class="contents">

            </div>
        </div>
    </div>
</template>
<style>
    .window{
        height:100%;
        width:100%;
        display:flex;
        flex-flow:row nowrap;
        align-items: center;
        position:relative;
    }
    .sideBar{
        width:20%;
        height:100%;
        background-image: linear-gradient(rgb(75, 186, 223),rgb(100, 98, 240), rgb(75, 186, 223),rgb(75, 186, 223));
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