<template>
  <div class="home">
    <Header />
    <section class="instrucciones">
      <p>
        Lorem ipsum es el texto que se usa habitualmente en diseño gráfico en
        demostraciones de tipografías o de borradores de diseño para probar el
        diseño visual antes de insertar el texto fina
      </p>
    </section>

    <section class="cuerpo">
      <article class="bocadilloIzq"><BocadilloIzq/></article>
      <article class="piezas"><Piezas /></article>
      <article class="bocadilloDer"><BocadilloDer /></article>
    </section>
    <Footer />
  </div>
</template>

<script>
// @ is an alias to /src

import Header from "@/components/Header.vue";
import Piezas from "@/components/Piezas.vue";
import Footer from "@/components/Footer.vue";
import BocadilloDer from "@/components/BocadilloDer.vue";
import BocadilloIzq from "@/components/BocadilloIzq.vue";

export default {
  name: "Home",
  components: {
    Header,
    Piezas,
    Footer,
    BocadilloIzq,
    BocadilloDer
  },
};
</script>
<style scoped>
.cuerpo {
  display: flex;
  width: 100%;
justify-content: space-evenly;
}
.instrucciones,
.boton {
  width: 100%;
  display: block;
}
.bocadilloIzq, .bocadilloDer{
  width: 33%;

}
.piezas{
  width: 560px;
   height: 750px;
}
</style>
