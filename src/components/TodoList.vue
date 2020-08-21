<template>
  <div class="container">
    <div class="row">
      <div class="col-12">TactLabs</div>
    </div>
    <div class="row">
      <NewTodo @on-addTodo="addTodo($event)" />
    </div>
    <div class="row">
      <p>Add create form</p>
    </div>
    <div class="row">
      <div class="col-12 col-lg-6">
        <ul class="list-group">
          <Todo
            v-for="(todo, index) in todos"
            :key="index"
            :todoString="todo.todoString"
            :completed="todo.completed"
            @on-delete="deleteTodo(todo)"
            @on-toggle="toggleTodo(todo)"
            @on-edit="editTodo(todo,$event)"
          />
        </ul>
      </div>
    </div>
  </div>
</template>
<script>
import Todo from "./Todo";
import NewTodo from "./NewTodo";
export default {
  components: {
    Todo,
    NewTodo,
  },
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
  methods: {
    addTodo(newTodo) {
      this.todos.push({
        todoString: newTodo,
        completed: false,
      });
    },
    toggleTodo(todo) {
      todo.completed = !todo.completed;
    },
    editTodo(todo, newTodoString) {
      todo.todoString = newTodoString;
    },
    deleteTodo(deleteTodo) {
      this.todos = this.todos.filter(
        (todo) => todo.todoString != deleteTodo.todoString
      );
    },
  },
};
</script>
<style scoped>
div {
  color: #fff;
}
</style>