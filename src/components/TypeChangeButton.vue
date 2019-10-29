<template>
  <button 
    type="button"
    class="btn"
    :class="buttonClass"
    @click="changeType"
  >
    {{ label }}
  </button>
</template>
<script>
export default {
  props: ['active', 'label'],
  computed: {
    buttonClass() {
      return this.active ? 'btn-primary' : 'btn-secondary';
    }
  },
  methods: {
    changeType() {
      this.$emit('click');
    }
  }
}
</script>