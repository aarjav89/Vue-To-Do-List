<template>
    <div>
    <h1> Aarjav's To-Do List </h1>
    <input type="text" v-model=task>
     <button @click="add()">Add</button>
        <!-- whatever u type in text box appears in the console-> vue section -->
        <h1> There are {{tasks.length}} tasks in your list</h1>

         <!-- code to display array items -->
        <ul>
            <li v-for="(t,index) in tasks" :key="index" @click="remove(index)"> <!-- assume we are using for-each loop wherein t is the actual content -->
                {{t}}
            </li>
        </ul>
    </div>

</template>

<script>
    export default{
        data(){
            return{
            task:"",
                tasks:[]
            }
        }, // end data

        methods:{
            add() {
                this.tasks.push(this.task)
                this.task=""
            },

            remove(index)
            {
                this.tasks.splice(index,1)
            }
        }

    }
</script>