<template>
  <div>
    <b-container>
      <b-input-group>
        <b-form-input type="text" v-model="value" />
        <b-input-group-append>
          <b-button variant="success" @click="handleAddTodo()">送信</b-button>
        </b-input-group-append>
      </b-input-group>
    </b-container>
  </div>
</template>

<script>
export default {
  name: 'TodoForm',
  data() {
    return {
      value: '',
    };
  },
  methods: {
    handleAddTodo() {
      this.$emit('handleParentAddTodo', this.value);
      this.value = '';
      // eslint-disable-next-line no-console
      console.log(this.value);
    },
  },
};
</script>

<style scoped></style>
