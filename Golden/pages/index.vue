<template>
  <div>
    <div class="text-xl text-center min-h-screen">
      <div class="">
        <Book></Book>

        <!-- <Karta></Karta> -->
      </div>
    </div>
    <div
      class="
        min-h-screen
        bg-yellow-600
        flex flex-col
        justify-center
        md:flex-row md:justify-start md:content-center
      "
    >
      <div>
        <img
          src="https://map02.eniro.no/geowebcache/service/tms1.0.0/map2x/13/4502/5779.png?c=2710559445&v=123"
          class="p-5 w-full md:w-auto rounded"
        />
      </div>
      <div class="flex flex-col">
        <h1 class="text-5xl m-5 text-center underline underline-offset-4">
          Platsen tipsar
        </h1>
        <img :src="books[8].img" class="px-5 pb-5 w-full md:w-auto rounded" />
      </div>
    </div>
  </div>
</template>

<script>
import BokLista from '../components/BokLista.vue'
import Karta from '../components/Karta.vue'
import Buttons from '/components/Buttons.vue'
import NavBar from '/components/NavBar.vue'

export default {
  components: { BokLista, Karta },
  name: 'IndexPage',
  Buttons,
  NavBar,

  data () {
    return {
      books: [],
    }
  },
  async fetch () {
    this.books = await fetch(
      "http://localhost:5000/books"
    ).then(res => res.json())
  },

}
</script>
