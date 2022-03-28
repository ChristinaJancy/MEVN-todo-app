<template>
  <div>
    <h1>Editing a todo</h1>
    <div v-for="item in todo" :key="item._id">
      <span>
        <b>Author:</b>
        {{ item.author }}</span
      >
      <br />
      <span> <b>Todo Item: </b>{{ item.todo }}</span>
    </div>
    <hr />

    <input type="text" placeholder="Author" v-model="state.newAuthor" />
    <span>Test: {{ state.newAuthor }} </span>
    <br />

    <input type="text" placeholder="Todo" v-model="state.newTodoItem" />
    <span>Test: {{ state.newTodoItem }} </span>
    <br /><br />

    <button @click="editTodo()">Update item</button>
    <hr />
  </div>
</template>

<script>
import todocrud from "../modules/todocrud";
export default {
  setup() {
    const { editTodo, state, getSpecificTodo, todo, todoId } = todocrud();

    getSpecificTodo(todoId);

    return { todo, todoId, editTodo, state };
  },
};
</script>

<style lang="scss" scoped>
</style>