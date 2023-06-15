<template>
  <section>
    <ul>
      <li v-for="todoItem in todoItems" class="shadow"  :key="todoItem.id">
        <i class="fa-solid fa-square-check"></i>
        {{ todoItem }}
        <i class="fa-solid fa-trash-can"></i>
    </li>
    </ul>
  </section>
</template>

<script>
export default {
  data() {
    return {
      todoItems: [],
    };
  },
  created() {
    if (localStorage.length > 0) {
      for (var i = 0; i < localStorage.length; i++) {
        this.todoItems.push(localStorage.key(i));
      }
    }
  },
};
</script>

<style scoped>
li {
  list-style: none;
  padding-top: 10px;

}
</style>
