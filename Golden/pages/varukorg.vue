<template>

<div>
<div v-for="user of books" :key="user.id">
  <h1> {{user.name}} </h1>
  <div>
    {{ user.varukorg[0] }}
    {{ user.varukorg[1] }}
    {{ user.varukorg[2] }}
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
      console.log(data)
      return data;
    //  this.books = data
      })
  },
},

  // book1 = books.Find(book=>book.id==varukorg.id)
}
</script>

<style>

</style>
