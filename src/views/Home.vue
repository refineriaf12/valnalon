<template>
  <div class="home">
    <Header />
    <section class="instrucciones">
      <p>
        Instruciones de como jugar con cada parte del Robot; se puedem mover,
        girar, transformar dando el  "clic" sobre la pieza correspiente. y colocarla dentro del lienzo donde cada niño/a
        desee; para volver a empezar solo hay que reiniciar la pagina , ademas
        se puede guardar la imagen de la composicion del Robot en el boton que
        pone descarga
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
  margin-top: 20px;
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
</style>
