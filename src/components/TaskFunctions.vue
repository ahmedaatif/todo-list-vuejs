<template>
    <div class="d-flex justify-content-between align-items-center">
        <button class="btn btn-success" @click="addNewTask">
            <i class="bi-plus me-1"></i>
            Add Task
        </button>

        <span class="text-muted">Number of Tasks: {{ tasksLength }}</span>
    </div>
</template>

<script>
export default {
    name: 'TaskFunctions',
    props: {
        tasksLength: Number,
        
    },
    emits: ['add-task'],
    methods: {
        addNewTask() {
            this.$emit('add-task');
        }
    },
}

</script>

<style>

</style>

