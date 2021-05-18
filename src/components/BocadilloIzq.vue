<template>
  <div>
    <div class="bocadillo-izquierda">
      <h1>
        La cabeza: Mas o menos grande segun tu capacidad de pensar y organizar
      </h1>
    </div>

    <div class="bocadillo-izquierda">
      <h1>
        Los ojos: Más o menos grandes,según sea tu capacidad de observar
        larealidad, la propia yla del entorno
      </h1>
    </div>

    <div class="bocadillo-izquierda">
      <h1>
        El tronco: Más o menos grande según sea tu capacidad de “estructurar” y
        relacionarte con tu equipo de trabajo.
      </h1>
    </div>

    <div class="bocadillo-izquierda">
      <h1>
        La nariz : Más o menos grande según sea tu “olfato” para percibir
        ocasiones y oportunidades
      </h1>
    </div>

    <div class="bocadillo-izquierda">
      <h1>
        Los brazos y manos: Más o menos largos según tu capacidad de “llegar”
        con la acción,de hacer(tus habilidades más prácticas)
      </h1>
    </div>
  </div>
</template>

<script>
export default {
  name: "BocadilloIzq",
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
div {
  display: flex;
  justify-content: flex-start;
  margin: 20px 25px;
  flex-direction: column;
}

.bocadillo-izquierda {
  margin-right: 80px;
  position: relative;
  background: white;
  border: 5px solid #8c52ff;
  box-shadow: 1px 12px 31px rgba(0, 0, 0, 0.5);
  font-size: 15px;
  color: #8c52ff;
  padding: 25px;
}
.bocadillo-izquierda:after,
.bocadillo-izquierda:before {
  left: 100%;
  top: 50%;
  border: solid transparent;
  content: "";
  height: 0;
  width: 0;
  position: absolute;
  pointer-events: none;
}
.bocadillo-izquierda:after {
  border-color: rgba(158, 81, 255, 0);
  border-left-color: white;
  border-width: 20px;
  margin-top: -20px;
}
.bocadillo-izquierda:before {
  border-color: rgba(235, 255, 181, 0);
  border-left-color: #8c52ff;
  border-width: 27px;
  margin-top: -27px;
}
</style>
