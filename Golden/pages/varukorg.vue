<template>
<div>
  {{ book1 }}
</div>
</template>

<script>
export default {
  data () {
    return {
      books: []
    }
  },
  async fetch () {
    this.books = await fetch(
      "http://localhost:5000/customers"
    ).then(res => res.json())
  },
  book1 = books.Find(book=>book.id==varukorg.id)
}
</script>

<style>

</style>
