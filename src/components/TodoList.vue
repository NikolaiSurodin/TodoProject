<template>
  <div>

    <todo-item v-for="(todo, i) of todos"
               v-bind:todo="todo"
               :key="todo.id"
               v-on:remove-todo="removeTodo"
               v-bind:index="i"
    ></todo-item>
  </div>
</template>
<script>

import TodoItem from "@/components/TodoItem";

export default {
  props: ['todos'],
  components: {
    TodoItem
  },
  methods: {
    removeTodo(id) {
this.$emit('remove-todo', id)
    }
  }
}

</script>

<style scoped>

</style>