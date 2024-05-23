<template>
  <div id="app">
    <h1>Library Book Borrowing System</h1>
    <BookList :books="books" @book-selected="displaySelectedBook" />
    <div v-if="selectedBook" class="selected-book">
      <h3>Selected Book</h3>
      <p><strong>Title:</strong> {{ selectedBook.title }}</p>
      <p><strong>Author:</strong> {{ selectedBook.author }}</p>
      <p><strong>Year:</strong> {{ selectedBook.year }}</p>
    </div>
  </div>
</template>

<script>
import BookList from './components/BookList.vue';

export default {
  name: 'App',
  components: {
    BookList
  },
  data() {
    return {
      books: [
        { id: 1, title: '1984', author: 'George Orwell', year: 1949 },
        { id: 2, title: 'To Kill a Mockingbird', author: 'Harper Lee', year: 1960 },
        { id: 3, title: 'The Great Gatsby', author: 'F. Scott Fitzgerald', year: 1925 }
      ],
      selectedBook: null
    };
  },
  methods: {
    displaySelectedBook(book) {
      this.selectedBook = book;
    }
  }
};
</script>

<style>
#app {
  font-family: Arial, sans-serif;
  text-align: center;
}

.selected-book {
  margin-top: 20px;
  padding: 10px;
  border: 1px solid #ccc;
}
</style>
