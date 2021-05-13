<template>
  <div class="home">
    <Header />
    <Piezas />
    <Footer />
  </div>
</template>

<script>
// @ is an alias to /src
// import Robot from '@/components/Robot.vue'
import Header from "@/components/Header.vue";
import Piezas from "@/components/Piezas.vue";
import Footer from "@/components/Footer.vue";



export default {
  name: "Home",
  components: {
    Header,
    Piezas,
    Footer,
  },
};
</script>
