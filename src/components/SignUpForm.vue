<template>
    <keep-alive>
        <component @step="checkStep" :is="componentName"/>
    </keep-alive>
    <p v-if="notFill" class="warning">
        {{error}}
    </p>
</template>
<script>
    import SignUpStep1 from './SignUpStep1'
    import SignUpStep2 from './SignUpStep2'
    export default{
        components : {
            SignUpStep1,
            SignUpStep2
        },
        emits:[
            'addUser'
        ],
        data(){
            return {
                componentName: 'sign-up-step-1',
                step1Data:'',
                step2Data:'',
                notFill : false,
                ready : false,
                userInfo : '',
                error : ''
            }
        },
        methods:{
            checkStep(data){
                if(data[data.length-1] == 'step-1'){
                    if(data[0] && data[2] && data[3]){
                        this.componentName = 'sign-up-step-2';
                        this.step1Data = data.slice(0, -1);
                        this.ready = true;
                        this.notFill = false;
                    }else{
                        this.error = 'Please fill all the required field';
                        this.notFill = true;
                    }
                }else{
                    if(data[data.length-1] == 'ready'){
                        this.step2Data = data.slice(0, -1);
                        this.userInfo = this.step1Data.concat(this.step2Data);
                        this.$emit('addUser', this.userInfo);
                    }else{
                        this.step2Data = data.slice(0, -1);
                        this.componentName='sign-up-step-1';

                    }
                }
            },
        }
    }
</script>
<style>
    warning{
        color: rgb(187, 12, 12);
    }
</style>
