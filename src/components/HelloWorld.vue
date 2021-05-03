<template>
  <div class="hello">
    
    <figure class="tamaño_M">
      <img
        src="@/assets/robot/cabeza.svg"
        alt=""
        class="active"
        id="cabeza_M"
      />
      </figure>

      <figure class="tamaño_M">
      <img
        src="@/assets/robot/orejaD.svg"
        alt=""
        class="active"
        id=""
      />
      </figure>

      

     
      
      
    
    <figure class="tamaño_M">
      <img src="@/assets/robot/boca.svg" alt="" class="active" id="cabeza_M" />
    </figure>
    <figure class="tamaño_M">
      <img src="@/assets/robot/nariz.svg" alt="" class="active" id="cabeza_M" />
    </figure>
    <figure class="tamaño_M">
      <img src="@/assets/robot/ojos.svg" alt="" class="active" id="cabeza_M" />
    </figure>

    <figure class="tamaño_M">
      <img
        src="@/assets/robot/torso.svg"
        alt=""
        class="active"
        id=""
      />
      </figure>

      <figure class="tamaño_M">
      <img
        src="@/assets/robot/corazon.svg"
        alt=""
        class="active"
        id=""
      />
      </figure>

      <figure class="tamaño_M">
      <img
        src="@/assets/robot/brazoD.svg"
        alt=""
        class="active"
        id=""
      />
      </figure>

      <figure class="tamaño_M">
      <img
        src="@/assets/robot/piernas.svg"
        alt=""
        class="active"
        id=""
      />
      </figure>

      <figure class="tamaño_M">
      <img
        src="@/assets/robot/pieD.svg"
        alt=""
        class="active"
        id=""
      />
      </figure>

       <figure class="tamaño_M">
      <img
        src="@/assets/robot/orejaI.svg"
        alt=""
        class="active"
        id=""
      />
      </figure>

       <figure class="tamaño_M">
      <img
        src="@/assets/robot/brazoI.svg"
        alt=""
        class="active"
        id=""
      />
      </figure>
       <figure class="tamaño_M">
      <img
        src="@/assets/robot/pieI.svg"
        alt=""
        class="active"
        id=""
      />
      </figure>

    <canvas id="crear_robot"></canvas>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
};

window.onload = function () {
  let canvas = document.getElementById("crear_robot");

  let ctx = canvas.getContext("2d");

  var robot = document.getElementsByClassName("active");
  ctx.scale(0.3, 0.3);
  ctx.drawImage(robot[8], 140, 280, 180, 200 ); //piernas
  ctx.drawImage(robot[1], 280, 55, 55, 55 );//oreja derecha
  ctx.drawImage(robot[10], 108, 55, 55, 55 );//oreja izq.
  ctx.drawImage(robot[5], 150, 130, 155, 155 );//torso
  ctx.drawImage(robot[0], 150, 0 );//cabeza
  ctx.drawImage(robot[2], 203, 108, 40, 12 );//boca
  ctx.drawImage(robot[3], 215, 80, 15, 15 );//nariz
  ctx.drawImage(robot[4], 193, 71, 60, 10 );//ojos
  ctx.drawImage(robot[6], 210, 190, 40, 40 );//corazon
  ctx.drawImage(robot[7], 291, 210, 65, 120 );//brazo derecho
  ctx.drawImage(robot[11], 100, 210, 65, 120 );//brazo izq
  ctx.drawImage(robot[9], 255, 455, 90, 35  );//pie derecho
  ctx.drawImage(robot[12], 118, 455, 90, 35  );//pie izq.

  console.log(robot[0], robot[1], robot[2], robot[3], robot[4], robot[5], robot[6], robot[7], robot[8], robot[9], robot[10],robot[11],robot[12]);
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
figure {
  padding: 0.5vw;
  cursor: pointer;
}

.active {
  border: 3px solid purple;
  border-radius: 50%;
}

.tamaño_S {
  width: 2.5vw;
  height: 2.5vw;
}
.tamaño_M {
  width: 3vw;
  height: 3vw;
}
.tamaño_L {
  width: 3.5vw;
  height: 3.5vw;
}

canvas {
  width: 1000px;
  height: 650px;
  border: 6px solid orange;
  display: block;
}
</style>
