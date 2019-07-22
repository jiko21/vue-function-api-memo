<template>
  <div class="hello">
    <b-input-group class="mt-3">
      <b-form-input v-model="text" required placeholder="write todo..." />
      <b-input-group-append>
        <b-button variant="primary" @click="addTodo">Add</b-button>
      </b-input-group-append>
    </b-input-group>
    <b-list-group>
      <b-list-group-item v-for="(todo, i) in todos" :key="i">
        <b-container class="bv-example-row">
          <b-row>
            <b-col class="todo-text" cols="8">{{ todo }}</b-col>
            <b-col>
              <b-button variant="danger" @click="deleteTodo">
                Delete
              </b-button>
            </b-col>
          </b-row>
        </b-container>
      </b-list-group-item>
    </b-list-group>
  </div>
</template>
<script>
import {value} from 'vue-function-api';

export default {
  setup() {
    const text = value('');
    const todos = value([]);

    const addTodo = () => {
      if (text.value !== '') {
        todos.value.push(text.value);
        text.value = '';
      }
    };
    const deleteTodo = (i) => {
      todos.value.splice(i, 1);
    };
    return {
      text,
      todos,
      addTodo,
      deleteTodo,
    };
  },
};
</script>
<style lang="scss" scoped>
.todo-text {
  align-items: center;
  justify-content: center;
  display: flex;
}
</style>
