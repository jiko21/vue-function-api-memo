<template>
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
</template>
<script>
export default {
  props: ['todos', 'deleteTodo'],
};
</script>

<style lang="scss" scoped>
.todo-text {
  align-items: center;
  justify-content: center;
  display: flex;
}
</style>
