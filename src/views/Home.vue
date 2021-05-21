<template>
  <div class="home">
    <Header />
    <section class="instrucciones">
      <p>
        <span>Diseña tu Robot jugando con las diferentes partes.</span> Cada parte se puede hacer
        más grande o más pequeña, se puede mover, girar o colocar donde quieras.
        Lee lo que representa cada pieza, haz “clic” sobre la pieza y juega.
        Para volver a empezar sólo tienes que “reiniciar la página”. Al final te
        podrás descargar TU RETRATO ROBOT. ¡Adelante!
      </p>
    </section>

    <section class="cuerpo">
      <article class="bocadilloIzq"><BocadilloIzq /></article>
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
    BocadilloDer,
  },
};
</script>
<style scoped>
.cuerpo {
  display: flex;
  width: 100%;
  justify-content: space-evenly;
  margin-bottom: 130px;
}
.instrucciones {
  width: 100%;
  display: flex;
  margin: 20px 0;
  color: #9e51ff;
  justify-content: center;
}
.instrucciones p {
  padding: 20px;
  text-align: center;
  width: 80%;
  border: 5px solid #9e51ff;
  box-shadow: 1px 12px 31px rgba(0, 0, 0, 0.5);
}
.bocadilloIzq,
.bocadilloDer {
  width: 33%;
}
.piezas {
  width: 560px;
  height: 750px;
}
span{
  font-weight:800;
}
</style>
