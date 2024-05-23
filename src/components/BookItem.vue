<template>
    <div @click="selectBook">
      <slot></slot> <!-- Display book title using slot -->
    </div>
  </template>
  
  <script>
  export default {
    name: 'BookItem',
    props: {
      book: Object
    },
    methods: {
      selectBook() {
        this.$emit('book-selected', this.book);
      }
    }
  };
  </script>
  
  <style scoped>
  div {
    cursor: pointer;
    padding: 10px;
    border: 1px solid #ccc;
    margin: 5px 0;
  }
  div:hover {
    background-color: #f0f0f0;
  }
  </style>
  