<template>
<div>
  <h1>{{ title }}</h1>
    <ul>
      <book-item :book="book" v-for="book in books" :key="book.title">
        {{ book.title }} : {{ book.author }}
      </book-item>
    </ul>
  <h2></h2>
</div>
</template>
<script>
import BookItem from "./BookItem";
export default {
  name: "BookList",
  components: {
    BookItem
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
  }
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

