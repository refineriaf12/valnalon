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

   </div>
    
</template>

<script>
export default {
  name: "Bocadillo",
};


</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
div {
  display: flex;
  justify-content: space-around;
  margin: 15px 0;
}


.bocadillo-izquierda {
  height: 100px;
  width: 300px;
  position: relative;
  background: #9e51ff;
  border: 5px solid orange;
  box-shadow: 1px 5px 13px rgba(0, 0, 0, 0.5);
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
  border-left-color: #9e51ff;
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
  height: 100px;
  width: 300px;
  position: relative;
  background: #9e51ff;
  border: 5px solid orange;
  box-shadow: 1px 12px 31px rgba(0, 0, 0, 0.5);
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
  border-right-color: #9e51ff;
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
