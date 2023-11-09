<template>
    <div 
    class="side-bar-item" 
    :companyOrProjectName="localCompanyOrProjectName"
    :companyLogo="localCompanyLogo"
    >
        <div class="company-logo">
            <img v-if=haveCompanyLogo :src="localCompanyLogo" alt="C">
            <span v-else>{{localCompanyOrProjectName}}</span>
        </div>
        <div>
            {{localCompanyOrProjectName}}
        </div>
    </div>
</template>
<script>
export default {
    components:{
        
    },
    props:[
        'companyOrProjectName',
        'companyLogo'
    ],
    data(){
        return{
           options:false, 
           "localCompanyOrProjectName":this.companyOrProjectName,
           "localCompanyLogo":this.companyLogo,
            "haveCompanyLogo":true
        }
    },
    methods:{

    },

}
</script>
<style scoped>
.side-bar-item{
    display: flex;
    flex-flow: row nowrap;
    align-items: center;
    gap:10px;
    justify-content: flex-start;
    padding : 2px 5px;
    background-color: rgba(255, 255, 255, 0.25);
    width:90%;
    height: 50px;
    font-family:'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
    font-size:1.2em;
    color : grey;
}
.side-bar-item:hover{
    background-color: rgba(255, 255, 255, 0.40);
}
.company-logo{
    max-height :40px;
    max-width: 40px;
    border-radius:50%;
    border : 1px solid green;
    display:flex;
    justify-content:center;
    align-items:center;
    overflow:hidden;
    font-family:'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
    font-size:1.2em;
    color:green;
}
.company-logo{
    height:2.5em;
    width:2.5em;
}
</style>