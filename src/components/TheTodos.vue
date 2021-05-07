<template>
<new-todo></new-todo>
<todo-list></todo-list>
</template>

<script>
import newTodo from "./newTodo.vue";
import todoList from "./todoList.vue";

export default {
  components: {
    newTodo,todoList
  },
  data() {
    return {
    todos: [
       
      ],
    };
  },
  provide(){
      return{
          todos:this.todos,
      }
  }
};
</script>