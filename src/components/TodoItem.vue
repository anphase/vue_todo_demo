<template>
<!-- binding the is-complete css on the condition that the todo is completed -->
    <div class="todo-item" v-bind:class="{'is-complete':todo.completed}">
        <p>
            <!-- Add event and define in script methods -->
            <input type="checkbox" v-on:change="markComplete">
            {{todo.title}}
            <!-- Emit the delete event to pass it up to the Todos object -->
            <button @click="$emit('del-todo', todo.id)" class="del">x</button>
            </p>
    </div>
</template>

<script>
export default {
    name: "TodoItem",
    props: ["todo"],
    methods: {
        markComplete() {
            // Toggle
            this.todo.completed = !this.todo.completed;
        }
    }
}
</script>


<style scoped>
    .todo-item {
        background: #f4f4f4;
        padding: 10px;
        border-bottom: 1px #ccc dotted;
    }

    .is-complete {
        text-decoration: line-through;
    }

    .del {
        background: #ff0000;
        color: #fff;
        border: none;
        padding: 5px 9px;
        border-radius: 50%;
        cursor: pointer;
        float: right;
    }
</style>
