<template>
  <div class="der">
    <div class="bocadillo-derecha">
      <h1>
        <span>Las Orejas</span>: Más o menos grandes segun tu capacidad de escuchar
      </h1>
    </div>
    <div class="bocadillo-derecha">
      <h1>
        <span>La Nariz</span>: Más o menos grande según sea tu “olfato” para percibir ocasiones
        y oportunidades.
      </h1>
    </div>
    <div class="bocadillo-derecha">
      <h1>
        <span>El Corazón</span>: Más o menos grande según la calidad de tus valores 
        y de tu compromiso social
      </h1>
    </div>
     <div class="bocadillo-derecha">
      <h1>
        <span>Los Brazos y Las Manos</span>: Más o menos largos según tu capacidad de “llegar” 
        con la acción,de hacer(tus habilidades más prácticas).
      </h1>
    </div>
     <div class="bocadillo-derecha">
      <h1>
        <span>Las Piernas</span>: Más o menos grandes según sea tu capacidad de “recorrer” 
        la realidad,la calle,de pasar a la acción, de tomar la iniciativa para proponer cosas.
      </h1>
    </div>
    
  </div>
</template>
<script>
export default {
    name: "BocadilloDer",
};
</script>
<style scoped>
.der{
padding:50px;
}
.bocadillo-derecha {
  width: 100%;
  padding:15px;
  position: relative;
  background: white;
  border: 5px solid #9e51ff;
  box-shadow: 1px 12px 31px rgba(0, 0, 0, 0.5);
  margin: 15px 0;
  color:#9e51ff;
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
  border-right-color: white;
  border-width: 20px;
  margin-top: -20px;
}
.bocadillo-derecha:before {
  border-color: rgba(235, 255, 181, 0);
  border-right-color: #9e51ff;
  border-width: 27px;
  margin-top: -27px;
}
span{
  font-weight:800;
  }
</style>
