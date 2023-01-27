<template>
    <div class="container border rounded mt-5 p-3">
        <TaskFunctions @add-task="addNewTask" :tasksLength="tasks.length"></TaskFunctions>
        <TaskList @trigger-update="updateTasks" @delete-task="deleteTask" :tasks="tasks"></TaskList>
        <div class="text-center my-5" v-if="tasks?.length <= 0">
            <h2 class="text-muted">There are no tasks. Horray!</h2>
        </div>
    </div>
</template>

<script>
import TaskFunctions from './TaskFunctions.vue';
import TaskList from './TaskList.vue';
export default {
    name: 'TodoContainer',
    components: {
        TaskList,
        TaskFunctions
    },
    data() {
        return {
            tasks: [],
        }
    },
    methods: {
        deleteTask(id){
            this.tasks = this.tasks.filter((task)=> task.id !== id);

            this.updateTasks();
        },
        addNewTask() {
            this.tasks.push({id: this.tasks.length, text: ""});

            this.updateTasks();
        },
        updateTasks(){
            localStorage.setItem('todo_ahmedaatif', JSON.stringify(this.tasks));
        }
    },
    created() {
        //this created function runs when the component is loaded/created
        let tasksFromLocalStorage = JSON.parse(localStorage.getItem('todo_ahmedaatif'));

        if(tasksFromLocalStorage != null){
            this.tasks = tasksFromLocalStorage;
        }
    }
}

</script>

<style>

</style>

