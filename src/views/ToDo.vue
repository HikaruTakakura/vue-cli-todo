<template>
  <div>
    <div v-for="(todo, index) in todos" :key="index">
      {{ todo }}
      <button v-on:click="deleteTodo(index)">消す</button>
    </div>
    <input type="text" v-model="inputValue" />
    <button v-on:click="addTodo">add</button>
  </div>
</template>

<script>
// 保存
// todos が更新されたとき localStorage にほうりこむ
// 最初に読み込む

export default {
  data() {
    return {
      todos: [],
      inputValue: ""
    };
  },
  methods: {
    addTodo() {
      this.todos.push(this.inputValue);
      localStorage["todos"] = JSON.stringify(this.todos);
    },
    deleteTodo(index) {
      this.todos.splice(index, 1);
      localStorage["todos"] = JSON.stringify(this.todos);
    }
  },
  mounted() {
    this.todos = JSON.parse(localStorage["todos"]);
  }
};
</script>

<style lang="scss" scoped></style>
