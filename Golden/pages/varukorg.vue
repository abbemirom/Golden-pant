<template>

<div>
<div v-for="user of books" :key="user.id">
  <h1 >{{user.name}} </h1>
  <div v-for="book of user.varukorg" :key="book">
    book
  </div>
  <!-- {{ book1 }} -->

</div>
</div>
</template>

<script>
export default {
  data () {
    return {
      books: []
    }
  },
  created()
  {
    this.fetch();
    console.log(this.books)
  },
methods:{
async fetch () {
    this.books = await fetch(
      "http://localhost:5000/customers"
    ).then(res => {
      const data = res.json()
      this.books = data
      })
  },
},

  // book1 = books.Find(book=>book.id==varukorg.id)
}
</script>

<style>

</style>
