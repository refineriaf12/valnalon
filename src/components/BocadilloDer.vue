<template>
  <div class="der">
    <div class="bocadillo-derecha">
      <h1>Las orejas: Mas o menos grandes segun tu capacidad de escuchar</h1>
    </div>
    <div class="bocadillo-derecha">
      <h1>Las orejas: Mas o menos grandes segun tu capacidad de escuchar
          Las orejas: Mas o menos grandes segun tu capacidad de escuchar
          Las orejas: Mas o menos grandes segun tu capacidad de escuchar
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
padding:30px;
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
</style>
