<template>
    <div class="container">
        <AddTask v-show="showAddTask" @add-task="addTask" />
        <Tasks :tasks="tasks" @toggle-reminder="toggleReminder" @delete-task="deleteTask" />
    </div>
</template>
  
<script >
import AddTask from "../components/AddTask.vue"
import Tasks from '../components/Tasks.vue';
export default {
    name: "Home",
    components: {
        Tasks,
        AddTask,
    },
    data() {
        return { tasks: [] }
    },
    props:{
        showAddTask: Boolean,
    },
    methods: {
        async deleteTask(id) {
            if (confirm("are yu sure to remove this task")) {
                const res = await fetch(`http://localhost:5000/tasks/${id}`, {
                    method: 'DELETE',
                })

                res.status === 200
                    ? (this.tasks = this.tasks.filter((task) => task.id !== id))
                    : alert('Error deleting task')
            }

        },
        async toggleReminder(id) {
            const taskToToggle = await this.fetchTask(id)
            const updTask = { ...taskToToggle, reminder: !taskToToggle.reminder }

            const res = await fetch(`http://localhost:5000/tasks/${id}`, {
                method: 'PUT',
                headers: {
                    'Content-type': 'application/json',
                },
                body: JSON.stringify(updTask),
            })

            const data = await res.json()

            this.tasks = this.tasks.map((task) =>
                task.id === id ? { ...task, reminder: data.reminder } : task
            )
        },
        async newTask(task) {
            const res = await fetch('http://localhost:5000/tasks', {
                method: 'POST',
                headers: {
                    'Content-type': 'application/json',
                },
                body: JSON.stringify(task),
            })

            const data = await res.json()

            this.tasks = [...this.tasks, data]
        },
        async fetchData() {
            try {
                const response = await fetch('http://localhost:5000/tasks');
                const data = await response.json();
                return data;
            } catch (error) {
                console.error('Error:', error);
                return []
            }
        },
        async fetchTask(id) {
            const res = await fetch(`http://localhost:5000/tasks/${id}`);

            const data = await res.json()

            return data
        },


    },
    async created() {
        this.tasks = await this.fetchData();
    }

}

</script>