<template>
  <div>
    <ul>
      <li id="cabeza">
        <figure class="tamaño_S" @click ="TamañoMenos">
          <img src="@/assets/robot/cabeza.svg" alt="" class="" id="" />
        </figure>
        <figure class="tamaño_M selected">
          <img src="@/assets/robot/cabeza.svg" alt="" class="" id="" />
        </figure>
        <figure class="tamaño_L">
          <img src="@/assets/robot/cabeza.svg" alt="" class="active" id="" />
        </figure>
      </li>
    </ul>
    <canvas id="crear_robot" height="500" width="500"></canvas>
  </div>
</template>

<script>
export default {
  name: "Cabeza",

  data(){
    return{
      el:'#cabeza',
      vueCanvas:null,
      ejex: 0,
      ejey:0,
      ancho: 80,
      alto: 80,

    }
  },
    mounted(){
        let canvas = document.getElementById("crear_robot");
        let ctx = canvas.getContext("2d");
        this.vueCanvas = ctx;
        var robot = document.getElementsByClassName("active");
        this.vueCanvas.drawImage(robot[0], this.ejex, this.ejey, this.ancho, this.alto); //cabeza
        
        
    },
    methods: {
       

       tamañoMenos(){
          this.ancho -=10;
          this.alto -= 10;
          

       }
    },
     beforeMount(){
       
     
     }

  
  }








</script>




<style scoped>
div {
  display: flex;
  justify-content: space-around;
  margin: 15px 0;
}

figure {
  width: 80px;
  height: 80px;
  cursor: pointer;
  display: flex;
  padding: 15px;
}
img {
  width: 100%;
  height: 100%;
}
li {
  margin: 15px 0;
  display: flex;
}

.selected {
  border: 3px solid purple;
  border-radius: 50%;
}

.tamaño_S img {
  transform: scale(0.8);
}
.tamaño_M img {
  transform: scale(1);
}
.tamaño_L img {
  transform: scale(1.2);
}

canvas {
  border: 6px solid orange;
  display: block;
}
</style>
