<template>
  <nav class="sticky w-full p-6 bg-yellow-600 border-b-2">
    <div class="flex items-center justify-between">

      <!-- Mobile toggle & varukorg -->
      <div class="flex items-center">
        <div class="mr-5">
          <button @click="drawer">
            <svg
              class="h-8 w-8 fill-current text-black"
              fill="none" stroke-linecap="round"
              stroke-linejoin="round" stroke-width="2"
              viewBox="0 0 24 24" stroke="currentColor">
                <path d="M4 6h16M4 12h16M4 18h16"></path>
            </svg>
          </button>
        </div>

        <div class="mr-5 dropdown">
          <button @click="dropDown" class="dropbtn">
            <img src="~/static/shoppingbasket.png" class="h-8 w-10" />
          </button>

          <div class="dropdown-content" id="myDropdown">
            <h1>content</h1>
          </div>
        </div>
      </div>

      <!-- Navbar -->
      <!-- <div class="hidden md:block">
        <ul class="flex space-x-8 text-sm font-sans">
          <li><a href="#" class="active border-b-2 border-blue-500 pb-1">Home</a></li>
          <li><a href="#" class="">Services</a></li>
          <li><a href="#" class="">Features</a></li>
          <li><a href="#" class="">FAQ</a></li>
          <li><a href="#" class="">Contact</a></li>
          <li><a href="#" class="cta bg-blue-500 hover:bg-blue-600 px-3 py-2 rounded text-white font-semibold">Sign Up</a></li>
        </ul>
      </div> -->

      <!-- Dark Background Transition -->
      <transition
        enter-class="opacity-0"
        enter-active-class="ease-out transition-medium"
        enter-to-class="opacity-100"
        leave-class="opacity-100"
        leave-active-class="ease-out transition-medium"
        leave-to-class="opacity-0"
      >
        <div @keydown.esc="isOpen = false" v-show="isOpen" class="z-10 fixed inset-0 transition-opacity">
            <div @click="isOpen = false" class="absolute inset-0 bg-black opacity-50" tabindex="0"></div>
        </div>
      </transition>

      <!-- Drawer Menu -->
      <aside class="p-5 transform top-0 left-0 w-64 bg-white fixed h-full overflow-auto ease-in-out transition-all duration-300 z-30" :class="isOpen ? 'translate-x-0' : '-translate-x-full'">

        <div class="close">
          <button class="absolute top-0 right-0 mt-4 mr-4" @click="isOpen = false">
            <svg
              class="w-6 h-6"
              fill="none" stroke-linecap="round"
              stroke-linejoin="round" stroke-width="2"
              viewBox="0 0 24 24" stroke="currentColor">
              <path d="M6 18L18 6M6 6l12 12"></path>
            </svg>
          </button>
        </div>

        <ul class="divide-y font-sans">
          <li><button @click="navigate('/')" class="my-4 inline-block">Home</button></li>
          <li><button @click="navigate('/about')" class="my-4 inline-block">About</button></li>
        </ul>

      </aside>

      <!-- Header logo -->
      <div>
        <h1 class="font-body text-4xl">My Books</h1>
      </div>

      <!-- Header logo -->
      <div>
        <button>Login</button>
      </div>
    </div>
  </nav>
</template>

<script>

/*window.onclick = function(event) {
  if (!event.target.matches('#dropbtn')) {
    var dropdowns = documentGetElementByIdName("dropdown-content");
    var i;
    for (i = 0; i < dropdowns.length; i++) {
      var openDropdown = dropdowns[i];
      if (openDropdown.classList.contains('show')) {
        openDropdown.classList.remove('show');
      }
    }
  }
}*/

export default {
  data() {
    return {
      isOpen: false
    };
  },
  methods: {

    dropDown() {
      document.getElementById("myDropdown").classList.toggle("show");
    },

    drawer() {
      this.isOpen = !this.isOpen;
    },
    navigate(path) {
        this.$router.push(path);
        this.drawer();
    }
  },
  watch: {
    isOpen: {
      immediate: true,
      handler(isOpen) {
        if (process.client) {
          if (isOpen) document.body.style.setProperty("overflow", "hidden");
          else document.body.style.removeProperty("overflow");
        }
      }
    }
  },
  mounted() {

    document.addEventListener("keydown", e => {
      if (e.keyCode == 27 && this.isOpen) this.isOpen = false;
    });
  }
};
</script>

<style>
.dropdown {
  position: relative;
  display: inline-block;
}

.dropdown-content {
  display: none;
  position: absolute;
  background-color: #f1f1f1;
  min-width: 160px;
  box-shadow: 0px 8px 16px 0px rgba(0,0,0,0.2);
  z-index: 1;
  width: 100%;
  overflow: auto;
}

.dropdown-content h1 {
  color: black;
  padding: 12px 16px;
  text-decoration: none;
  display: block;
}

.show {display:block;}
</style>
