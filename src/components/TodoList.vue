<template>
  <div>
    <h1>TodoList</h1>
  </div>
</template>
<script>
export default {
  data() {
    return {
      todos: [
        { todoString: "quit job", completed: false },
        { todoString: "kill yourself", completed: false },
        { todoString: "go outside", completed: false },
        { todoString: "work 16 hours", completed: true },
      ],
    };
  },
};
</script>
<style scoped>
h1 {
  color: #fff;
}
</style>