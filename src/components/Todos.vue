<template>
<div>
    <div v-bind:key="todo.id" v-for="todo in todos">
        <!-- Also emit del-todo when the del-todo event triggered in the todo item -->
        <TodoItem v-bind:todo="todo" v-on:del-todo="$emit('del-todo', todo.id)" />
    </div>
</div>
</template>

<script>
import TodoItem from './TodoItem.vue';

export default {
    name: "Todos",
    components: {
        TodoItem
    },
    props: ["todos"]
}
</script>

<style scoped>

</style>
