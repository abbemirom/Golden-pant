<template>
  <div>
    <h1 class="taxt-xl">Böcker</h1>
    <div class="flex flex-row justify-center mt-36">
      <div>
        <img :src="books[20].img" class="h-60 w-full" />
        <h4>{{ books[20].title }}</h4>
      </div>
      <div class="flex content-center">
        <button>
          <svg
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 24 24"
            stroke-width="1.5"
            stroke="currentColor"
            class="w-6 h-6"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              d="M8.25 4.5l7.5 7.5-7.5 7.5"
            />
          </svg>
        </button>
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
