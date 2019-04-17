<template>
  <div>
    <p>Completed Tasks: {{todos.filter(todo => {return todo.done === true}).length}}</p>
    <p>Pending Tasks: {{todos.filter(todo => {return todo.done === false}).length}}</p>
    <todo  v-on:delete-todo="deleteConfirmBox" v-for="todo in todos" v-bind:todo="todo" v-bind:key="todo.project"></todo>
  </div>
</template>
<script type = "text/javascript" >
import sweetalert from 'sweetalert';
import Todo from './Todo';
export default {
  name: 'TodoList',
  props: ['todos'],
   components: {
    Todo,
  },
  methods:{
    deleteTodo(todo){
      const todoIndex = this.todos.indexOf(todo);
      this.todos.splice(todoIndex, 1);
    },
    deleteConfirmBox(){
      sweetalert("Are you sure you want to delete this to do?", {
        buttons: ["No!", "Yes!"],
      });
    }

  }
}
</script>
