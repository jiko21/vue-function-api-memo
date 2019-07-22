<template>
  <div class="props">
    <h1>Props版</h1>
    <AddTodo :addTodo="addTodo" />
    <TodoList :todos="todos" :deleteTodo="deleteTodo" />
  </div>
</template>
<script>
import {value} from 'vue-function-api';
import AddTodo from '@/components/AddTodo.vue';
import TodoList from '@/components/TodoList.vue';

export default {
  components: {
    AddTodo,
    TodoList,
  },
  setup() {
    const todos = value([]);
    const addTodo = (todo) => {
      todos.value.push(todo);
    };
    const deleteTodo = (i) => {
      todos.value.splice(i, 1);
    };
    return {
      addTodo,
      deleteTodo,
      todos,
    };
  },
};
</script>
<style lang="scss" scoped>
.props {
  margin: 0 20%;
}
</style>
