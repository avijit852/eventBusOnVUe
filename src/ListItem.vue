<template>
    <div>
        <h3>This is my List Items</h3>
        <div>
            <table border="1" >
                <tr>
                    <td>ID</td>
                    <td>Job Name</td>
                    <td>Job Duration</td>
                </tr>  
                <tr v-if="foundData">
                    <th colspan="3">Sorry no more data found</th>
                </tr>    
                <tr v-else v-for="item in listAll" :key="item.id">
                    <td>{{item.id}}</td>
                    <td>{{item.jobName}}</td>
                    <td>{{item.duration}}</td>
                </tr>
                <tr>

                </tr>
            </table>
        </div>
        <Item></Item>
    </div>
</template>


<script>
import Item from './Item'
export default {
    components:{
        Item,
    },
    data(){
        return{
            listAll:[],
            foundData:true
        }
    },
    created(){
        eventBus.$on('listItem',(data)=>{
            this.listAll = data
            this.foundData = false
        })
    }
}
</script>