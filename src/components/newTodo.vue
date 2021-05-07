<template>
  <h1>ToDo App (with components)</h1>
  <form @submit.prevent="addNewTodo">
    <label for="addTodo">New ToDo</label>
    <input type="text" name="addTodo" v-model="newTodo" />
    <button>Add New ToDo</button>
  </form>
</template>

<script>
export default {
    inject: ["todos"],
    data() {
    return {
      newTodo: "",
    };
  },
  methods: {
    addNewTodo() {
      if (this.newTodo.trim() == "") {
        return;
      }
      this.todos.unshift({ done: false, content: this.newTodo });
      this.newTodo = "";
      // console.log(this.todos)
    },
  },
};
</script>


<style lang="scss" >
  h1 {
      text-align: center;
    }
    form {
      display: flex;
      flex-direction: column;
      width: 100%;
      label {
        font-weight: bold;
      }
      input,
      button {
        padding: 01rem 0;
        margin: 0.5rem 0;
        border: 2px solid rgb(92, 168, 255);
        border-radius: 5px;
        outline: none;
      }
      input {
        background-color: #ffffff;
        color: rgb(65, 64, 64);
      }
      button {
        background-color: rgb(92, 168, 255);
        font-size: 18px;
        font-weight: bold;
        border: none;
      }
    }
    </style>