<template>
    <form @submit.prevent="onSubmit">
        <!-- <textarea v-model="task"></textarea> -->
        <input type="text" v-model="task">
        <button type="submit">Add task</button>
    </form>
</template>

<script>
export default {
    data() {
        return {
            task:''
        }
    },
    methods: {
        onSubmit() {
            console.log(this.task)
            if (this.task.length !== 0) {
                console.log('fus')
                const newTask = {
                    id: Date.now(),
                    task: this.task,
                    completed: false
                }
                this.$emit('addTask', newTask)
            }            
        }
    }
}
</script>