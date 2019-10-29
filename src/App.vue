<template>
  <div class="container">
    <Header />
    <UserInput
      @add-todo="addTodo"
    />
    <TodoList 
      :todos="currentTodos"
      @toggle-todo="toggleTodo"
    />
    <TypeChange 
      :currentType="type"
      @change-type="changeType"
    />
  </div>
</template>
<script>
import Header from './components/Header.vue';
import UserInput from './components/UserInput.vue';
import TodoList from './components/TodoList.vue';
import TypeChange from './components/TypeChange.vue';

export default {
  data() {
    return {
      todos: [],
      type: 'all'
    };
  },
  computed: {
    currentTodos() {
      if (this.type === 'all') {
        return this.todos;
      }

      if (this.type === 'done') {
        return this.todos.filter(todo => todo.done === true);
      }

      if (this.type === 'notyet') {
        return this.todos.filter(todo => todo.done === false);
      }
    }
  },
  methods: {
    addTodo(title) {
      this.todos.push({
        title,
        done: false
      })
    },
    toggleTodo(index) {
      this.todos[index].done = ! this.todos[index].done;
    },
    changeType(type) {
      this.type = type;
    }
  },
  components: {
    Header,
    UserInput,
    TodoList,
    TypeChange
  }
}
</script>