<template>

  <div>
    <h2>Задачи на день</h2>
    <router-link to="/">Home</router-link>
    <hr>
    <add-todo @add-todo="addTodo"></add-todo>

    <todo-list
        v-if="todos.length"
        v-bind:todos="todos"
        v-on:remove-todo="removeTodo"></todo-list>

      <p v-else>Задач на сегодня нет!</p>




  </div>

</template>

<script>
import TodoList from '@/components/TodoList'
import AddTodo from '@/components/AddTodo'

export default {
  name: 'app',
  data() {
    return {
      todos: [],
      filter:'all'
    }
  },

  methods: {
    removeTodo(id) {
      this.todos = this.todos.filter(t => t.id !== id)
    },
    addTodo(todo) {
      this.todos.push(todo)
    }
  },
  components: {
    TodoList,
    AddTodo
  }
}

</script>
<style>
p{
  color: green;
}
</style>