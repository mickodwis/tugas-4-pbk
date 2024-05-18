<template>
    <div>
      <h3>GrandChild Component</h3>
      <button @click="emitDataToChild">Click Me (GrandChild)</button>
    </div>
  </template>
  
  <script>
  export default {
    methods: {
      emitDataToChild() {
        this.$emit('grand-child-clicked', 'Data from GrandChild');
      }
    }
  };
  </script>
  