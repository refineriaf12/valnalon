<template>
  <div class="home">
    <Header />

    <main class="app">
      <Bocadillos />
      <Piezas />
    </main>

    <Footer />
  </div>
</template>

<script>
// @ is an alias to /src

import Header from "@/components/Header.vue";

import Footer from "@/components/Footer.vue";

import Bocadillos from "@/components/Bocadillos.vue";
import Piezas from "@/components/Piezas.vue";


export default {
  name: "Home",
  components: {
    Header,
    Bocadillos,
    Piezas,
    Footer,
  },
};
</script>

<style>
.app {
  display: flex;
  justify-content: flex-start;
}
</style>
