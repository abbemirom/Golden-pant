<template>
  <div>
    <div class="text-left">Böcker</div>
    <div class="flex flex-row justify-center">
      <div class="w-1/4 h-20 md:h-40 bg-black my-10 mx-2 text-white rounded">
        {{ books[0].title }}
        <img :src="books[0].img" />
      </div>
      <div class="w-1/4 h-20 md:h-40 bg-black my-10 mx-2 text-white rounded">
        {{ books[1].title }}
        <img :src="books[1].img" />
      </div>
      <div class="w-1/4 h-20 md:h-40 bg-black my-10 mx-2 text-white rounded">
        {{ books[2].title }}
        <img :src="books[2].img" />
      </div>
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
  async fetch () {
    this.books = await fetch(
      "http://localhost:5000/books"
    ).then(res => res.json())
  }
}
</script>>

<style>
</style>
