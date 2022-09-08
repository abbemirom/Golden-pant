<template>
  <div>
    <div class="text-xl text-center mt-4 min-h-screen">
      Böcker
      <div class="">
        <BokLista></BokLista>
        <!-- <Karta></Karta> -->
      </div>
    </div>
    <div class="min-h-screen bg-yellow-600 flex flex-col justify-center">
      <div>
        <img
          src="https://map02.eniro.no/geowebcache/service/tms1.0.0/map2x/13/4502/5779.png?c=2710559445&v=123"
          class="ml-5"
        />
      </div>
    </div>
  </div>
</template>

<script>
import BokLista from '../components/BokLista.vue'
import Karta from '../components/Karta.vue'
export default {
  components: { BokLista, Karta },
  name: 'IndexPage'
}
</script>
