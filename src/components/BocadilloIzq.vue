<template>
   <div class="izq">
    <div class="bocadillo-izquierda">
      <h1>
        La cabeza: Mas o menos grande segun tu capacidad de pensar y organizar
      </h1>
    </div>
    <div class="bocadillo-izquierda">
      <h1>
        La cabeza: Mas o menos grande se gun tu capacidad de pensar y organizargun tu capacidad de pensar y organizar gun tu capacidad de pensar y organizar
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


.izq{
 padding:30px;

}
.bocadillo-izquierda {
  width: 100%;
  padding:15px;
  position: relative;
  background: white;
  border: 5px solid #9e51ff;
  box-shadow: 1px 5px 13px rgba(0, 0, 0, 0.5);
  margin:15px 0;
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



</style>
