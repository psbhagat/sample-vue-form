<template>
  <ul>
    <li :class="{ active: modelValue === 'poor' }">
      <button type="button" @click="activateMethod('poor')">Poor</button>
    </li>
    <li :class="{ active: modelValue === 'average' }">
      <button type="button" @click="activateMethod('average')">Average</button>
    </li>
    <li :class="{ active: modelValue === 'great' }">
      <button type="button" @click="activateMethod('great')">Great</button>
    </li>
  </ul>
</template>

<script>
export default {
  props: ['modelValue'],
  emits: ['update:modelValue'],
  methods: {
    activateMethod(option) {
      this.activeOption = option;
      this.$emit('update:modelValue', this.activeOption);
    },
  },
};
</script>

<style scoped>
.active {
  background-color: rgb(247, 199, 247);
}
ul {
  list-style: none;
  margin: 0 0.5rem 0;
  padding: 0;
  display: flex;
}

li {
  margin: 10px;
}

button {
  font: inherit;
  border: none;
  background-color: transparent;
  cursor: pointer;
  border: 1px solid black;
}
</style>