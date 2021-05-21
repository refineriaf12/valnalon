<template>
  <div class="izq">
    <div class="bocadillo-izquierda">
      <h1>
        <span>La Cabeza</span>: Más o menos grande segun tu capacidad de pensar y organizar
      </h1>
    </div>
    <div class="bocadillo-izquierda">
      <h1>
        <span>Los Ojos</span> :Más o menos grandes,según sea tu capacidad de observar la realidad,
        la propia y la del entorno
      </h1>
    </div>
    <div class="bocadillo-izquierda">
      <h1>
        <span>La Boca</span>: Más o menos grande según sea la capacidad de comunicarte, de hacer
        llegar tus mensajes
      </h1>
    </div>
    <div class="bocadillo-izquierda">
      <h1>
        <span>El Tronco</span>: Más o menos grande según sea tu capacidad de “estructurar” y relacionar 
        te con tu equipo de trabajo
      </h1>
    </div>
    <div class="bocadillo-izquierda">
      <h1>
        <span>Los Pies</span>: Más o menos grandes según sean los “apoyos”,la base social,la conexión 
        con la realidad
      </h1>
    </div>
    
  </div>
</template>

<script>
export default {
  name: "BocadilloIzq",
};
</script>

<style scoped>
.izq {
  padding: 50px;
}
.bocadillo-izquierda {
  width: 100%;
  padding: 15px;
  position: relative;
  background: white;
  border: 5px solid #9e51ff;
  box-shadow: 1px 5px 13px rgba(0, 0, 0, 0.5);
  margin: 15px 0;
  color: #9e51ff;
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
  border-left-color: #9e51ff;
  border-width: 27px;
  margin-top: -27px;
}
span{
  font-weight:800;
}
</style>
