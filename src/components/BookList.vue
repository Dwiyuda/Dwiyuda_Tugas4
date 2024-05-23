<template>
    <div>
      <h2>Book List</h2>
      <BookItem 
        v-for="book in books" 
        :key="book.id" 
        :book="book" 
        @book-selected="handleBookSelected"
      >
        {{ book.title }}
      </BookItem>
    </div>
  </template>
  
  <script>
  import BookItem from './BookItem.vue';
  
  export default {
    name: 'BookList',
    components: {
      BookItem
    },
    props: {
      books: Array
    },
    methods: {
      handleBookSelected(book) {
        this.$emit('book-selected', book);
      }
    }
  };
  </script>
  
  <style scoped>
  h2 {
    font-family: Arial, sans-serif;
  }
  </style>
  