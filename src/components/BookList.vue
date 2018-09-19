<template>
<div>
  <h1>{{ title }}</h1>
    <ul>
      <book-item :book="book" v-for="book in books" :key="book.title">
        {{ book.title }} : {{ book.author }}
      </book-item>
    </ul>
  <h2></h2>
  <book-form @addBook='appendBook'></book-form>
</div>
</template>
<script>
import BookItem from "./BookItem";
import BookForm from "./BookForm";
export default {
  name: "BookList",
  components: {
    BookItem,
    BookForm
  },
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
    appendBook(bookTitle,bookAuthor){
      this.books.push({title: bookTitle, author: bookAuthor});
    }
  },
};
</script>

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

