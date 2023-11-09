<template>
    <div class="user-header">
        <div class="header-container">
                   <div class="logo-container">
            <slot name="logo">
                <span style="font-size:49px">LOGO</span>
            </slot>
       </div>
       <div class="navbar-container" style="font-size:20px;font-weight:600;color:black;">
            <slot name="navigation">
                <ul>
                    <li>Lorem ipsum</li>
                    <li>Lorem ipsum</li>
                    <li>Lorem ipsum</li>
                </ul>
            </slot>
       </div>
       <div class="user-profile">
            <slot name="user-picture">
                    <p style="font-size:46px;color:white;font-weight:700;">U</p>
            </slot>
       </div>
        </div>
    </div>
</template>
<script>
export default {
    
}
</script>
<style>
    .user-header{
        height:100%;
        width:100%;
        background-image: linear-gradient(to right, rgb(100, 98, 240), rgb(75, 186, 223), rgb(75, 186, 223), rgb(70, 68, 190));
        display :flex;
        justify-content: center;
        align-items: center;
        position:relative;
    }
    .header-container{
        height: 100%;
        width: 95%;
        display :flex;
        justify-content: space-between;
        align-items: center;
    }
    .user-profile{
        height: 50px;
        width: 50px;
        border:2px solid purple;
        border-radius: 50%;
        background-color: rgb(37, 163, 121);
        display: flex;
        justify-content: center;
        align-items: center;
    }
    ul{
        display: flex;
        flex-flow: row wrap;
        text-decoration:none;
        list-style: none;
    }
    ul li{
        padding:0px 15px;
        text-decoration:none;
    }
    ul li:hover{
        color:white;
        cursor:pointer;
    }
</style>