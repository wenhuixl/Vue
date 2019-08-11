<template>
    <li @click="dodelete">{{content}}</li>
</template>

<script>
    export default {
        name: "TodoItem",
        props: ['content', 'index'],
        methods: {
            dodelete () {
                this.$emit('mydelete', this.index)
            }
        }
    }
</script>

<style scoped>

</style>
