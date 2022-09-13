<template>
  <div>
    <div class="text-left">Böcker</div>
    <div class="flex flex-row justify-center">
      <div class="w-1/4 h-20 md:h-40 bg-black my-10 mx-2 text-white rounded">
        {{ books[0].title }}
      </div>
      <div class="w-1/4 h-20 md:h-40 bg-black my-10 mx-2 text-white rounded">
        {{ books[1].title }}
      </div>
      <div class="w-1/4 h-20 md:h-40 bg-black my-10 mx-2 text-white rounded">
        {{ books[2].title }}
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
