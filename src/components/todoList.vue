<template>
  <section>
    <ul>
      <li
        v-for="(todoItem, index) in propsdata"
        class="shadow"
        :key="todoItem.id"
      >
        <i class="checkBtn fa fa-check" aria-hidden="true"></i>
        {{ todoItem }}
        <span
          class="removeBtn"
          type="button"
          @click="removeTodo(todoItem, index)"
        >
          <i class="trash fa-solid fa-trash-can"></i>
        </span>
      </li>
    </ul>
  </section>
</template>

<script>
export default {
  props:['propsdata'],
  methods: {
    removeTodo(todoItem, index) {
      this.$emit('removeTodo',todoItem,index)
    },
  },
};
</script>

<style scoped>
li {
  justify-content: space-between;
  display: flex;
  list-style: none;
  padding: 10px;
}
.trash{
  cursor: pointer;
}
</style>
