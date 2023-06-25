<template>

    <div v-for="task in tasks">
    <Task :task="task" :key="task.id" @delete-task="$emit('delete-task',task.id )"   @toggle-reminder="$emit('toggle-reminder', task.id)"/>

    </div>
</template>

<script>
import Task from './Task.vue';
export default {
    name: "Tasks",
    props: {
        tasks: Array,
    },
    components:{Task},
    emits:['delete-task','toggle-reminder']
}

</script>