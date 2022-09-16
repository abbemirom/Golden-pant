<template>
  <div>
    <div class="text-left">Böcker</div>
    <div class="flex flex-row place-content-between mx-2 md:mx-20">
      <div class="flex flex-col w-1/3 md:1/4 h-20 md:h-40 my-10 mr-3">
        <div class="">
          <img :src="books[0].img" class="h-40 md:h-48 w-full" />
        </div>
        <div class="">
          {{ books[0].title }}
        </div>
      </div>
      <div class="flex flex-col w-1/3 md:1/4 md:h-40 my-10 mx-2">
        <div>
          <img :src="books[1].img" class="h-40 md:h-48 w-full" />
        </div>
        <div class="">
          {{ books[1].title }}
        </div>
      </div>
      <div class="flex flex-col w-1/3 md:1/4 md:h-40 my-10 mx-2 ml-3">
        <div>
          <img :src="books[2].img" class="h-40 md:h-48 w-full" />
        </div>
        <div class="">
          {{ books[2].title }}
        </div>
      </div>
    </div>
    <div class="flex flex-row place-content-between mx-2 md:mx-20 md:my-10">
      <div class="flex flex-col w-1/3 md:1/4 h-20 md:h-40 my-10 mr-3">
        <div class="">
          <img :src="books[20].img" class="h-40 md:h-48 w-full" />
        </div>
        <div class="">
          {{ books[20].title }}
        </div>
      </div>
      <div class="flex flex-col w-1/3 md:1/4 md:h-40 my-10 mx-2">
        <div>
          <img :src="books[150].img" class="h-40 md:h-48 w-full" />
        </div>
        <div class="">
          {{ books[150].title }}
        </div>
      </div>
      <div class="flex flex-col w-1/3 md:1/4 md:h-40 my-10 mx-2 ml-3">
        <div>
          <img :src="books[126].img" class="h-40 md:h-48 w-full" />
        </div>
        <div class="">
          {{ books[126].title }}
        </div>
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
</script>

<style>
</style>
