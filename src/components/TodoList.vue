<template>
    <div>
        <div 
        v-bind:key="todo.id" 
        v-for="todo in todoItems">
            <TodoItem 
            v-bind:todo="todo" 
            v-on:delete-todo="$emit('delete-todo', todo.id)" />
        </div>
    </div>
</template>

<script>
import TodoItem from './TodoItem.vue';
export default {
    name: "TodoList",
    components: {
        TodoItem
    },
    props: ["todoItems"]
}
</script>

<style>

</style>
