<template>
  <div class="mb-2">
    <template v-for="(todo, index) in todos">
      <div
        class="list-group-item"
        :class="{'list-group-item-primary' : todo.done}"
        :key="index"
        @click="toggleTodo(index)"
      >
        {{ todo.title }}
      </div>
    </template>
  </div>
</template>
<script>
export default {
  props: ['todos'],
  methods: {
    toggleTodo(index) {
      this.$emit('toggle-todo', index);
    }
  }
}
</script>