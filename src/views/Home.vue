<template>
  <div class="home">
    <Header />
<<<<<<< Updated upstream
    <!-- <div id="app"> -->

    <!-- Canvas -->
    <!-- <canvas id="c"></canvas> -->
    <!-- Add Rectangle Button -->
    <!-- <div>
        <button @click="drawRect">Add Rect</button>
    <button @click="subWidth">-</button>
    <button @click="addWidth">+</button>
      </div>
    </div> -->
    <Cabeza />
    <!-- <Robot /> -->
=======
    <main class="app">
      <Bocadillos />
      <Piezas />
    </main>
>>>>>>> Stashed changes
    <Footer />
  </div>
</template>

<script>
// @ is an alias to /src
// import Robot from '@/components/Robot.vue'
import Header from "@/components/Header.vue";
<<<<<<< Updated upstream
import Footer from "@/components/Footer.vue";
import Cabeza from "@/components/Cabeza.vue";
=======
import Bocadillos from "@/components/Bocadillos.vue";
import Piezas from "@/components/Piezas.vue";
import Footer from "@/components/Footer.vue";
>>>>>>> Stashed changes

export default {
  name: "Home",
  components: {
    Header,
<<<<<<< Updated upstream
=======
    Bocadillos,
    Piezas,
>>>>>>> Stashed changes
    Footer,
    Cabeza,
  },
};

</script>
<<<<<<< Updated upstream
<style scoped></style>
=======
<style>
.app {
  display: flex;
  justify-content: flex-start;
  
}
</style>
>>>>>>> Stashed changes
