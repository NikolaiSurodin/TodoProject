<template>

    <li>
    <span v-bind:class="{done:todo.completed}">
      <input type="checkbox" v-on:change="todo.completed = !todo.completed">
      <strong> {{index + 1}}</strong>
      {{todo.title}}
      <button v-on:click="$emit('remove-todo', todo.id)">&times;</button>
    </span>
    </li>



</template>
<script>
export default {
  props: {
    todo: {
      type: Object,
      required: true
    },
    index:Number
  }
}

</script>

<style scoped>
li {
  border: 1px solid #ccc;
  display: flex;
  justify-content: space-between;
  padding: 1rem 1rem;
  margin-bottom: 1rem;
}



input {
  margin-right: 1rem;
}

.done {
  text-decoration: line-through;
}
</style>