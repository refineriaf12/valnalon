<template>
  <div class="home">
    <Header />
    <main class="app">
      <section class="instruciones">
        <h1>
          orem Ipsum is simply dummy text of the rinting and typesetting
          industry. Lorem Ipsum has been the industry's standard dummy text ever
          since the 1500s, when an unknown printer took a galley of type and
          scrambled it to make a type specimen book . It has survived not only
          five centuries, but also the leap into electronic typesetting,
          remaining essentially unchanged.
        </h1>
      </section>
      <section class="principal">
        <BocadilloIzq />
        <Piezas />
        <BocadilloDer />
      </section>
      <section id="guardado">
        <button>
          <span>Guardado</span>
        </button>
      </section>
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
  justify-content: flex-start;
  text-align: center;
}
.instruciones {
  text-align: center;
  margin-left: 100px;
  margin-right: 100px;
  border: 5px solid orange;
  padding: 38px;
  margin-top: 10px;
}
.principal {
  display: flex;
  justify-content: space-around;
  width:100%;
}
#guardado {
  display: flex;
  align-items: center;
  justify-content: center;
  margin-top: 50px;
  margin-bottom: 120px;
 
}
button {
  border: 5px solid orange;
  background: #8c52ff;

  color: white;
  padding: 15px 50px;

  overflow: hidden;
  position: relative;
}

button:after {
  content: "";
  display: block;
  position: absolute;
  top: -36px;
  left: -100px;
  background: white;
  width: 60px;
  height: 125px;
  opacity: 40%;
  transform: rotate(-45deg);
}

button:hover:after {
  left: 120%;
  transition: all 600ms cubic-bezier(0.3, 1, 0.2, 1);
  -webkit-transition: all 600ms cubic-bezier(0.3, 1, 0.2, 1);
}

</style>
