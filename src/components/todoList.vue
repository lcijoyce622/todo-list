<template>
  <h2>ToDo List</h2>
  <p v-if="todos.length==0">Please add some todos.</p>
  <ul v-else>
    <li v-for="todo in todos" :key="todo" :class="{ donestyle: todo.done }">
      <span @click="newDone(todo)">
        <input type="checkbox" :id="todo" v-model="todo.done" />
        {{ todo.content }}</span
      >
      <button @click="removeTodo(todo)">Remove</button>
    </li>
  </ul>
</template>

<script>
export default {
  inject: ["todos"],
  methods: {
    removeTodo(todo) {
      const idx = this.todos.findIndex((idx) => idx === todo);
      this.todos.splice(idx, 1);
    },
    newDone(todo) {
      const idx = this.todos.findIndex((idx) => idx === todo);
      this.todos[idx].done = !this.todos[idx].done;
    },
  },
};
</script>
<style lang="scss" >
h2 {
  border-bottom: 2px solid;
  border-color: rgb(92, 168, 255);
  padding: 0.3rem 0;
}
ul {
  padding: 0;
  .donestyle {
    border-color: rgb(195, 223, 255);
    span {
      color: rgb(195, 223, 255);
      text-decoration: line-through;
    }
    button {
      color: rgb(92, 168, 255);
      background-color: rgb(195, 223, 255);
    }
  }
  li {
    display: flex;
    justify-content: space-between;
    align-items: center;
    border: 2px solid rgb(92, 168, 255);
    border-radius: 5px;
    margin: 1rem 0;
    padding: 0.8rem;
    span {
      // cursor: pointer;
      user-select: none;
    }
    button {
      padding: 0.4rem;
      font-weight: 700;
      border-radius: 5px;
      background-color: rgb(92, 168, 255);
      border: none;
    }
  }
}
</style>