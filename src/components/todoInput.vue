<template>
  <div>
    <input type="text" v-model="newTodoItem" />
    <button @click="addTodo">추가</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      newTodoItem: "",
    };
  },
  methods: {
    addTodo() {
      localStorage.setItem(this.newTodoItem, this.newTodoItem);
      console.log(this.newTodoItem);
      if (this.newTodoItem != "") {
        const value = this.newTodoItem && this.newTodoItem.trim();
        localStorage.setItem(value, value);
        this.clearInput();
      }
    },
    clearInput() {
      this.newTodoItem = "";
    },
  },
};
</script>

<style>
input{
    margin-right: 10px;
}
</style>
