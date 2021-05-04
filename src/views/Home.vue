<template>
  <div class="home">
    <Header />
    <Robot />
    <Footer />
  </div>
</template>

<script>
// @ is an alias to /src
import Robot from '@/components/Robot.vue'
import Header from '@/components/Header.vue'
import Footer from '@/components/Footer.vue'

export default {
  name: 'Home',
  components: {
    Robot, Header, Footer
  }
}
</script>
