<template>
  <div class="home">
    <Header />
    <Cabeza />
    <!-- <Robot /> -->
    <Footer />
  </div>
</template>

<script>
// @ is an alias to /src
// import Robot from '@/components/Robot.vue'
import Header from '@/components/Header.vue'
import Footer from '@/components/Footer.vue'
import Cabeza from '@/components/Cabeza.vue'

export default {
  name: 'Home',
  components: {
     Header, Footer, Cabeza
  }
}
</script>
