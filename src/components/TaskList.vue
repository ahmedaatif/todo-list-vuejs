<template>
    <div class="input-group mt-3" :key ="task.id" v-for="task in tasks">
        <input @blur="onBlur()" type="text" class="form-control" v-model="task.text">
        <button @click="onDelete(task.id)" class="btn btn-danger" type="button">
            <i class="bi-x me-1"></i>
            Remove
        </button>
    </div>
</template>

<script>
export default {
    name: 'TaskList',
    components: {
    },
    props: {
        tasks: Array, //this is what it recieves from the Todo Container
    },
    emits: ['delete-task', 'trigger-update'],
    methods: {
        onDelete(id) {
            this.$emit('delete-task', id)
        },
        onBlur(){
            this.$emit('trigger-update');
        }
    }
}
</script>