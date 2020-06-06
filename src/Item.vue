<template>
    <div>
        <button @click="doJobsList">To See All jobs</button>
    </div>
</template>


<script>
export default {
    data(){
        return{
            doJobs:[
                {id:1,jobName:'development', duration:'1 to 10 hr'},
                {id:2,jobName:'teching', duration:'1 to 8 hr'},
                {id:3,jobName:'coding', duration:'1 to 9 hr'},
                {id:4,jobName:'driver', duration:'1 to 7 hr'}
            ]
        }
    },
    methods:{
        doJobsList(){
            eventBus.$emit('listItem',this.doJobs);
        }
    }   
}
</script>