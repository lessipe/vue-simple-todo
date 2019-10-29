<template>
  <div class="input-group mb-2">
    <input 
      type="text" 
      class="form-control" 
      v-model="userInput"  
      @keyup.enter="addTodo"
    >
    <div class="input-group-append">
      <button class="btn btn-outline-secondary" @click="addTodo">
        추가
      </button>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      userInput: ''
    }
  },
  methods: {
    addTodo() {
      if (this.userInput === '') return;
      
      this.$emit('add-todo', this.userInput);
      this.userInput = '';
    }
  }
}
</script>