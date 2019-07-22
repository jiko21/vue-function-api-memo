<template>
  <b-input-group class="mt-3">
    <b-form-input v-model="text" required placeholder="write todo..." />
    <b-input-group-append>
      <b-button variant="primary" @click="onAddClick">Add</b-button>
    </b-input-group-append>
  </b-input-group>
</template>
<script>
import {value} from 'vue-function-api';

export default {
  props: ['addTodo'],
  setup(props) {
    const text = value('');
    const onAddClick = () => {
      if (text.value !== '') {
        props.addTodo(text.value);
        text.value = '';
      }
    };
    return {
      text,
      onAddClick,
    };
  },
};
</script>
