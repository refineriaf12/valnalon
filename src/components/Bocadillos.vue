<template>
  <div>
    <div class="bocadillo-izquierda">
      <h1>
        La cabeza: Mas o menos grande segun tu capacidad de pensar y organizar
      </h1>
    </div>

    <div class="bocadillo-derecha">
      <h1>Las orejas: Mas o menos grandes segun tu capacidad de escuchar</h1>
    </div>
    <div class="bocadillo-izquierda">
      <h1>
        Los ojos:Más o menos grandes,según sea tu capacidad de observar
        larealidad, la propia yla del entorno
      </h1>
    </div>
    <div class="bocadillo-derecha">
      <h1>La boca:Más o menos grande según sea la capacidad de comunicarte,
        de hacer llegar tus mensajes</h1>
    </div>
    <div class="bocadillo-izquierda">
      <h1>
        El tronco:Más o menos grande según sea tu capacidad de “estructurar” 
        y relacionarte con tu equipo de trabajo.
      </h1>
    </div>
    <div class="bocadillo-derecha">
      <h1>Los pies:Más o menos grandes según sean los “apoyos”,
        la base social,la conexión con la realidad</h1>
    </div>
    <div class="bocadillo-izquierda">
      <h1>
        La nariz :Más o menos grande según sea tu “olfato” 
        para percibir ocasiones y oportunidades
      </h1>
    </div>
    <div class="bocadillo-derecha">
      <h1>El corazón :Más o menos grande según la calidad de tus valores 
        y de tu compromiso social</h1>
    </div>
    <div class="bocadillo-izquierda">
      <h1>
        Los brazos y manos:Más o menos largos según tu capacidad de “llegar”
        con la acción,de hacer(tus habilidades más prácticas)
      </h1>
    </div>
    <div class="bocadillo-derecha">
      <h1>Las piernas: Más o menos grandes según sea tu capacidad de “recorrer” 
        la realidad,la calle,de pasar a la acción,de tomar la iniciativa para proponer cosas.</h1>
    </div>
  </div>
</template>

<script>
export default {
  name: "Bocadillos",
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
div {
  display: flex;
  justify-content: center;
  margin: 5px 20px;
  flex-direction: column;
}

.bocadillo-izquierda {
  height: 70px;
  width: 380px;
  margin-left: 80px;
  position: relative;
  background: #8C52FF;
  border: 5px solid orange;
  box-shadow: 1px 5px 13px rgba(0, 0, 0, 0.5);
  font-size:11px;
  color: white;
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
  border-left-color: #8C52FF;
  border-width: 20px;
  margin-top: -20px;
}
.bocadillo-izquierda:before {
  border-color: rgba(235, 255, 181, 0);
  border-left-color: orange;
  border-width: 27px;
  margin-top: -27px;
}
.bocadillo-derecha {
  height: 70px;
  width: 380px;
  margin-right: 80px;
  position: relative;
  background: #8C52FF;
  border: 5px solid orange;
  box-shadow: 1px 12px 31px rgba(0, 0, 0, 0.5);
  font-size:11px;
  color: white;
}
.bocadillo-derecha:after,
.bocadillo-derecha:before {
  right: 100%;
  top: 50%;
  border: solid transparent;
  content: "";
  height: 0;
  width: 0;
  position: absolute;
  pointer-events: none;
}
.bocadillo-derecha:after {
  border-color: rgba(158, 81, 255, 0);
  border-right-color: #8C52FF;
  border-width: 20px;
  margin-top: -20px;
}
.bocadillo-derecha:before {
  border-color: rgba(235, 255, 181, 0);
  border-right-color: orange;
  border-width: 27px;
  margin-top: -27px;
}
</style>
