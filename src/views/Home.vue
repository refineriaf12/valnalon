<template>
  <div class="home">
    <Header />
    <Konva/>
    <!-- <Robot /> -->
    <Footer />
  </div>
</template>

<script>
// @ is an alias to /src
// import Robot from '@/components/Robot.vue'
import Header from '@/components/Header.vue'
import Footer from '@/components/Footer.vue'
import Konva  from '@/components/Konva.vue'

export default {
  name: 'Home',
  components: {
     Header, Footer, Konva,
  }
}
</script>
