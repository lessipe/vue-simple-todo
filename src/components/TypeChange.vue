<template>
  <div>
    <TypeChangeButton 
      :active="currentType === 'all'"
      label="전체"
      @click="changeType('all')"
    />
    <TypeChangeButton 
      :active="currentType === 'done'"
      label="완료"
      @click="changeType('done')"
    />
    <TypeChangeButton 
      :active="currentType === 'notyet'"
      label="미완료"
      @click="changeType('notyet')"
    />
  </div>
</template>
<script>
import TypeChangeButton from './TypeChangeButton.vue';

export default {
  props: ['currentType'],
  methods: {
    changeType(type) {
      this.$emit('change-type', type);
    }
  },
  components: {
    TypeChangeButton
  }
}
</script>