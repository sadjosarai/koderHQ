<template>
    <div class="window">
        <slot>
            <h1>
                ERROR 404
            </h1>
            <h2>
                content not found
            </h2>
        </slot>
    </div>
</template>
<style scoped>
    .window{
        height:90vh;
        width:100vw;
        display:flex;
        flex-flow:column wrap;
        align-items: center;
        border:1px solid grey;
        border-radius:5px;
        position:relative;
    } 
</style>