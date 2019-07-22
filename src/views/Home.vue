<template>
  <div class="home">
    <h1>通常版</h1>
    <Todo />
  </div>
</template>

<script>
// @ is an alias to /src
import Todo from '@/components/Todo.vue';

export default {
  name: 'home',
  components: {
    Todo,
  },
};
</script>
<style lang="scss" scoped>
.home {
  margin: 0 20%;
}
</style>
