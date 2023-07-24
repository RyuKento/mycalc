<template >
 <b-container>
    <b-input-group prepend="タスク名">
     <b-form-input v-model="taskname"></b-form-input>
     <b-input-group-append>
        <b-button variant="outline-success" @click="addtask">タスク追加</b-button>
     </b-input-group-append>
    </b-input-group>
    <p >現在のタスク数：{{count}}/{{tasks.length}}</p>
   <b-table striped hover :items="tasks" :fields="fields">
    <template #cell(action)=task>
        <b-button size="sm" @click="completetask(task)" class="mr-2">
            <p>{{task.item.status}}</p>
        </b-button>
    </template>
    <template #cell(date)=date>
        <p>{{date.value.toLocaleString()}}</p>
    </template>
   </b-table>
 </b-container>
</template>

<script>
export default {
    data(){
        return{
            tasks:[],
            taskname:"",
            fields:[{key:'isActiv',sortable:true},{key:'date',sortable:true},'name',{key:'action'}],
            count:0,
        }
    },
    methods:{
        addtask(){
            let obj = {
              isActive :true,
              name : this.taskname,
              date : new Date(),
              status : "完了"
            }
            this.tasks.push(obj);

        },
        completetask(task){
            task.item.isActive = !task.item.isActive;
            if(task.item.isActive){
            task.item.status="完了";
            this.count--;
           }
            if(!task.item.isActive){
            task.item.status="未完";
            this.count++;
            }
        }
        
    }
}
</script>