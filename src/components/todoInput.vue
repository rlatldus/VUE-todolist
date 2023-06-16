<template>
  <div class="inputBox" >
    <input type="text" v-model="newTodoItem" placeholder="할일을 메모하세요" v-on:keyup.enter="addTodo"/>
    <span class="addContainer" @click="addTodo">
      <i class="addBtn fa fa-plus" aria-hidden="true"></i>
    </span>
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
        this.$emit('addTodo',value)
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
input:focus{
  outline:none;
}
.inputBox{
  background: white;
height: 50px;
line-height: 50px;
border-radius: 5px;
margin: 10px;
}
.inputBox input{
  border-style: none;
  font-size: 0.9rem;
}
.addContainer{
  float: right;
  background: linear-gradient(to right, #6478FB, #8763FB);
  display: inline-block;
  width: 3em;
  border-radius: 0 5px 5px 0;
}
.addBtn{
  color: white;
  vertical-align: middle;
}

</style>
