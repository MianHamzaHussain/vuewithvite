<template>

        <div class="header">
            <h1>{{ title }}</h1>

            <Button :color="showAddTask?'red':'green'" :text="showAddTask?'Close':'Add task'" @btn-click="$emit('toggle-show-add')" />
        </div>
</template>

<script>
import Button from './Button.vue';
export default {
    name: "Header",

    props: {
        title: String,
        showAddTask:Boolean,
    },
    components: {
        Button,
    }
}


</script>


<style scoped>
.header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-bottom: 20px;
}
</style>