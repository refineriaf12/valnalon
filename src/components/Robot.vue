<template>
  <div class="hello">
    <div>
      <ul>
        <li id="cabeza">
          <figure class="tamaño_S">
            <img src="@/assets/robot/cabeza.svg" alt="" class="" id="" />
          </figure>
          <figure class="tamaño_M selected">
            <img src="@/assets/robot/cabeza.svg" alt="" class="" id="" />
          </figure>
          <figure class="tamaño_L ">
            <img src="@/assets/robot/cabeza.svg" alt="" class="active" id="" />
          </figure>
        </li>
        <li id="orejas">
          <figure class="tamaño_S">
            <img src="@/assets/robot/orejaI.svg" alt="" class="" id="" />
            <img src="@/assets/robot/orejaD.svg" alt="" class="" id="" />
          </figure>
          <figure class="tamaño_M selected">
            <img src="@/assets/robot/orejaI.svg" alt="" class="" id="" />
            <img src="@/assets/robot/orejaD.svg" alt="" class="" id="" />
          </figure>
          <figure class="tamaño_L ">
            <img src="@/assets/robot/orejaI.svg" alt="" class="active" id="" />
            <img src="@/assets/robot/orejaD.svg" alt="" class="active" id="" />
          </figure>
        </li>
        <li id="ojos">
          <figure class="tamaño_S">
            <img src="@/assets/robot/ojos.svg" alt="" class="" id="" />
          </figure>
          <figure class="tamaño_M selected">
            <img src="@/assets/robot/ojos.svg" alt="" class="" id="" />
          </figure>
          <figure class="tamaño_L ">
            <img src="@/assets/robot/ojos.svg" alt="" class="active" id="" />
          </figure>
        </li>
        <li id="nariz">
          <figure class="tamaño_S">
            <img src="@/assets/robot/nariz.svg" alt="" class="" id="" />
          </figure>
          <figure class="tamaño_M selected">
            <img src="@/assets/robot/nariz.svg" alt="" class="" id="" />
          </figure>
          <figure class="tamaño_L ">
            <img src="@/assets/robot/nariz.svg" alt="" class="active" id="" />
          </figure>
        </li>
        <li id="boca">
          <figure class="tamaño_S">
            <img src="@/assets/robot/boca.svg" alt="" class="" id="" />
          </figure>
          <figure class="tamaño_M selected">
            <img src="@/assets/robot/boca.svg" alt="" class="" id="" />
          </figure>
          <figure class="tamaño_L">
            <img src="@/assets/robot/boca.svg" alt="" class="active" id="" />
          </figure>
        </li>
      </ul>
    </div>
    <div class="bocadillo-izquierda">
      <h1>
        La cabeza: Mas o menos grande segun tu capacidad de pensar y organizar
      </h1>
    </div>

    <canvas id="crear_robot" height="300" width="300"></canvas>
    <div class="bocadillo-derecha">
      <h1>Las orejas: Mas o menos grandes segun tu capacidad de escuchar</h1>
    </div>
    <div>
      <ul>
        <li id="torso">
          <figure class="tamaño_S">
            <img src="@/assets/robot/torso.svg" alt="" class="" id="" />
          </figure>
          <figure class="tamaño_M selected">
            <img src="@/assets/robot/torso.svg" alt="" class="" id="" />
          </figure>
          <figure class="tamaño_L ">
            <img src="@/assets/robot/torso.svg" alt="" class="active" id="" />
          </figure>
        </li>
        <li id="cozaron">
          <figure class="tamaño_S">
            <img src="@/assets/robot/corazon.svg" alt="" class="" id="" />
          </figure>
          <figure class="tamaño_M selected">
            <img src="@/assets/robot/corazon.svg" alt="" class="" id="" />
          </figure>
          <figure class="tamaño_L ">
            <img src="@/assets/robot/corazon.svg" alt="" class="active" id="" />
          </figure>
        </li>
        <li id="brazos">
          <figure class="tamaño_S">
            <img src="@/assets/robot/brazoI.svg" alt="" class="" id="" />
            <img src="@/assets/robot/brazoD.svg" alt="" class="" id="" />
          </figure>
          <figure class="tamaño_M selected">
            <img src="@/assets/robot/brazoI.svg" alt="" class="" id="" />
            <img src="@/assets/robot/brazoD.svg" alt="" class="" id="" />
          </figure>
          <figure class="tamaño_L ">
            <img src="@/assets/robot/brazoI.svg" alt="" class="active" id="" />
            <img src="@/assets/robot/brazoD.svg" alt="" class="active" id="" />
          </figure>
        </li>

        <li id="piernas">
          <figure class="tamaño_S">
            <img src="@/assets/robot/piernas.svg" alt="" class="" id="" />
          </figure>
          <figure class="tamaño_M selected">
            <img src="@/assets/robot/piernas.svg" alt="" class="" id="" />
          </figure>
          <figure class="tamaño_L">
            <img src="@/assets/robot/piernas.svg" alt="" class="active" id="" />
          </figure>
        </li>
        <li id="pies">
          <figure class="tamaño_S">
            <img src="@/assets/robot/pieI.svg" alt="" class="" id="pieI_S" />
            <img src="@/assets/robot/pieD.svg" alt="" class="" id="" />
          </figure>
          <figure class="tamaño_M selected">
            <img src="@/assets/robot/pieI.svg" alt="" class="" id="pieI_M" />
            <img src="@/assets/robot/pieD.svg" alt="" class="" id="" />
          </figure>
          <figure class="tamaño_L ">
            <img
              src="@/assets/robot/pieI.svg"
              alt=""
              class="active"
              id="pieI_L"
            />
            <img src="@/assets/robot/pieD.svg" alt="" class="active" id="" />
          </figure>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "Robot",
};

window.onload = function() {
  let canvas = document.getElementById("crear_robot");
  let ctx = canvas.getContext("2d");

  var robot = document.getElementsByClassName("active");
  ctx.imageSmoothingEnabled = false;
  ctx.scale(0.3, 0.3);
  ctx.drawImage(robot[10], 325, 500, 350, 450); //piernas
  ctx.drawImage(robot[1], 270, 115, 105, 125); //oreja izq.
  ctx.drawImage(robot[2], 615, 115, 105, 125); //oreja derecha
  ctx.drawImage(robot[6], 355, 280, 285, 255); //torso
  ctx.drawImage(robot[0], 350, 0); //cabeza
  ctx.drawImage(robot[5], 460, 215, 70, 30); //boca
  ctx.drawImage(robot[4], 478, 165, 30, 35); //nariz
  ctx.drawImage(robot[3], 425, 150, 140, 15); //ojos
  ctx.drawImage(robot[7], 450, 380, 100, 100); //corazon
  ctx.drawImage(robot[8], 225, 410, 160, 310); //brazo izq
  ctx.drawImage(robot[9], 605, 410, 160, 310); //brazo derecho
  ctx.drawImage(robot[11], 280, 900, 180, 65); //pie izq.
  ctx.drawImage(robot[12], 555, 890, 180, 65); //pie derecho

  console.log(
    robot[0],
    robot[1],
    robot[2],
    robot[3],
    robot[4],
    robot[5],
    robot[6],
    robot[7],
    robot[8],
    robot[9],
    robot[10],
    robot[11],
    robot[12]
  );
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
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
#pieI_S,
#pieI_M,
#pieI_L {
  width: 0.5px;
  height: 0.5px;
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

canvas {
  border: 6px solid orange;
  display: block;
}
</style>
