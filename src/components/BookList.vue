<template>
  <div class="booklist">
    <h1>{{ title }}</h1>
    <ul>
      <book-item v-for="book in books" v-bind:book="book"
        >{{ book.title }}:{{ book.author }}</book-item
      >
    </ul>
    <book-form @addBook="appendBook"></book-form>
  </div>
</template>

<script>
import BookItem from "./BookItem";
import BookForm from "./BookForm";

export default {
  name: "BookList",
  components: { BookItem, BookForm },
  data() {
    return {
      title: "All Books",
      books: [
        { title: "Self-Reliance", author: "Ralph Waldo Emerson" },
        { title: "American Gods", author: "Neil Gaiman" },
        { title: "Amusing Ourselves to Death", author: "Neil Postman" }
      ]
    };
  },
  methods: {
    appendBook(bookTitle, bookAuthor){
      this.books.push({ title: bookTitle, author: bookAuthor })
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1,
h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
</style>
