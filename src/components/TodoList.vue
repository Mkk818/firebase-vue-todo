<template>
  <b-container>
    <b-row :key="index" v-for="(todo, index) in todos" class="mt-2">
      <b-col cols="8" class="text-start">
        <h5>{{ todo.text }}</h5>
      </b-col>
      <b-col cols="4" class="text-end">
        <b-button>完了</b-button>
        <b-button @click="handleDeleteTodo(index)">削除</b-button>
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
export default {
  name: 'TodoList',
  props: ['todos'],
  methods: {
    handleDeleteTodo(index) {
      this.$emit('handleParentDeleteTodo', index);
    },
  },
};
</script>

<style scoped></style>
