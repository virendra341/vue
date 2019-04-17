<template>
<div>
   <todo-list v-bind:todos="todos"></todo-list>
   <create-todo  v-on:create-todo="createTodo"/>
</div>

</template>

<script>
import sweetalert from 'sweetalert';
import TodoList from './components/TodoList'
import CreateTodo from './components/CreateTodo'

export default {
  name: 'App',
  components: {
    TodoList,
    CreateTodo
  },
  data () {
    return {
      todos: [{
        title: 'Todo A',
        project: 'Project A',
        done: false,
        isEditing:true
      }, {
        title: 'Todo B',
        project: 'Project B',
        done: true,
        isEditing:false
      }, {
        title: 'Todo C',
        project: 'Project C',
        done: false,
        isEditing:true
      }, {
        title: 'Todo D',
        project: 'Project D',
        done: false,
        isEditing:false
      }]
    }
  },
  methods:{
    createTodo(newTodo){
      this.todos.push(newTodo);
      sweetalert('Success!', 'To-Do created!', 'success');

    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
