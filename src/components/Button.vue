<template>
    <button class="btn" :style="{ backgroundColor: color }" @click="onClick()">

        {{ text }}
    </button>
</template>


<script >
export default {
    name: "Button",
    props: {
        color: String,
        text: String,
    },
    methods: {
        onClick(){
            this.$emit('btn-click')
        }
    }

}
</script>

<style scoped></style>