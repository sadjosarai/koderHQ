<template>
    <div class="user-header">
       <div class="logo-container">
            <slot name="logo">
                <span style="font-size:49px">LOGO</span>
            </slot>
       </div>
       <div class="navbar-container" style="font-size:18px;color:white;">
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
</template>
<script>
export default {
    
}
</script>
<style scope>
    .user-header{
        height:70px;
        width:100vw;
        /* background-image: linear-gradient(to right rgb(70, 68, 190), rgb(75, 186, 223), rgb(75, 186, 223), rgb(75, 186, 223), rgb(70, 68, 190)); */
        background-color: rgba(140, 67, 209, 0.808);
        display :flex;
        justify-content: space-between;
        align-items: center;
        position:relative;
        padding: 0px 15px;
    }
    #user-profile{
        height: 60px;
        width: 60px;
        border-radius: 50%;
        background-color: rgb(37, 163, 121);
        display: flex;
        justify-content: center;
        align-items: center;
    }
    ul{
        text-decoration:none;
        display: flex;
        flex-flow: column nowrap;
    }
</style>