<template>
    <div>
      <h2>Child Component</h2>
      <button @click="emitDataToParent">Click Me</button>
      <grand-child @grand-child-clicked="handleGrandChildClicked">
        <template v-slot:default="slotProps">
          <p>{{ slotProps.message }}</p>
        </template>
      </grand-child>
    </div>
  </template>
  
  <script>
  import GrandChild from './GrandChild.vue';
  
  export default {
    components: {
      GrandChild
    },
    methods: {
      emitDataToParent() {
        this.$emit('child-clicked', 'Data from Child');
      },
      handleGrandChildClicked(data) {
        this.$emit('child-clicked', data);
      }
    }
  };
  </script>
  