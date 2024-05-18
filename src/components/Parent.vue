<template>
    <div>
      <h1>Parent Component</h1>
      <child @child-clicked="handleChildClicked">
        <template v-slot:default="slotProps">
          <p>{{ slotProps.message }}</p>
        </template>
      </child>
      <p>Data dari Child: {{ dataFromChild }}</p>
    </div>
  </template>
  
  <script>
  import Child from './Child.vue';
  
  export default {
    components: {
      Child
    },
    data() {
      return {
        dataFromChild: ''
      };
    },
    methods: {
      handleChildClicked(data) {
        this.dataFromChild = data;
      }
    }
  };
  </script>
  