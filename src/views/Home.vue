<template>
  <div class="todoList">
    <div class="container">
      <TodoList 
      v-bind:todoItems="todoItems" 
      v-on:delete-todo="deleteTodo"/>
      <AddTodo v-on:add-todo="addNewTodo"/>
    </div>    
  </div>
</template>

<script>
import TodoList from '../components/TodoList';
import AddTodo from '../components/AddTodo';
import axios from 'axios';

export default {
  name: 'Home',
  components: {
    TodoList,
    AddTodo
  },
  data() {
    return{
      todoItems: [
      ]
    }
  },
  methods: {
    deleteTodo(idToDelete){
      axios.delete(`https://jsonplaceholder.typicode.com/todos/${idToDelete}`)
        .then(res => {
          this.todoItems = this.todoItems.filter(todo => todo.id != idToDelete);
        })
        .catch(err => console.log('err'));
      
    },
    addNewTodo(newTodo){
      const {title, completed} = newTodo;
      axios.post('https://jsonplaceholder.typicode.com/todos', {
        title,
        completed
      })
        .then(res => {
          this.todoItems = [...this.todoItems, newTodo];
        })
        .catch(err => console.log('err'));
    }
  },
  created() {
    axios.get('https://jsonplaceholder.typicode.com/todos?_limit=10')
      .then(res => {
        this.todoItems = res.data;
      })
      .catch(err => console.log('err'));
  }
}
</script>

<style>  
</style>
