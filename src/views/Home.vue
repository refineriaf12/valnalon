<template>
  <div class="home">
    <Header />
  <fieldset class="instruciones">
    <h1>orem Ipsum is simply dummy text of the rinting
       and typesetting industry. Lorem Ipsum has been the industry's 
       standard dummy text ever since the 1500s, when an unknown printer 
       took a galley of type and scrambled it to make a type specimen book
       . It has survived not only five centuries, but also the leap into
        electronic typesetting, remaining essentially unchanged.
         </h1>
  </fieldset>
    <main class="app">
      <BocadilloIzq />
      <Piezas />
      <BocadilloDer/>
    </main>

    <Footer />
  </div>
</template>

<script>
// @ is an alias to /src

import Header from "@/components/Header.vue";
import Footer from "@/components/Footer.vue";
import BocadilloDer from "@/components/BocadilloDer.vue";
import BocadilloIzq from "@/components/BocadilloIzq.vue";
import Piezas from "@/components/Piezas.vue";

export default {
  name: "Home",
  components: {
    Header,
    BocadilloIzq,
    Piezas,
    BocadilloDer,
    Footer,
  },
};
</script>

<style>
.app {
  display: flex;
  justify-content: flex-start;
  text-align: center;
}
.instruciones {
  display: flex;
  justify-content: center;
  margin-bottom: 50px;
}
</style>
