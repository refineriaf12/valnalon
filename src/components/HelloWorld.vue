<template>
  <div class="hello">

    <figure class="tamaño_S">
      <img src="@/assets/robot/cabeza.svg" alt="" id="cabeza_S">
    </figure>
    <figure class="tamaño_M">
      <img src="@/assets/robot/cabeza.svg" alt="" class="active" id="cabeza_M">
    </figure>
    <figure class="tamaño_L">
      <img src="@/assets/robot/cabeza.svg" alt="" id="cabeza_L">
    </figure>


    <figure class="tamaño_M">
      <img src="@/assets/robot/boca.svg" alt="" class="active" id="cabeza_M">
    </figure>
    <figure class="tamaño_M">
      <img src="@/assets/robot/nariz.svg" alt="" class="active" id="cabeza_M">
    </figure>
    <figure class="tamaño_M">
      <img src="@/assets/robot/ojos.svg" alt="" class="active" id="cabeza_M">
    </figure>
    
    <canvas id="crear_robot"></canvas>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld'
}

window.onload = function() {
  let dpi = window.devicePixelRatio;
  //get canvas
  let canvas = document.getElementById('myCanvas');
  //get context
  let ctx = canvas.getContext('2d');
  function fix_dpi() {
    //get CSS height
    //the + prefix casts it to an integer
    //the slice method gets rid of "px"
    let style_height = +getComputedStyle(canvas).getPropertyValue("height").slice(0, -2);
    //get CSS width
    let style_width = +getComputedStyle(canvas).getPropertyValue("width").slice(0, -2);
    //scale the canvas
    canvas.setAttribute('height', style_height * dpi);
    canvas.setAttribute('width', style_width * dpi);
  }
  
  var robot = document.getElementsByClassName("active");
  ctx.drawImage(robot[0], 50, 10, 70, 40);
  ctx.drawImage(robot[1], 76, 38, 20, 3);
  ctx.drawImage(robot[2], 82, 31, 8, 5);
  ctx.drawImage(robot[3], 71, 30, 30, 2);

  console.log(robot[0], robot[1], robot[2], robot[3])
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  figure{
    padding:0.5vw;
    cursor:pointer;
  }

  .active{
    border: 3px solid purple;
    border-radius: 50%;
  }

  .tamaño_S{
    width: 2.5vw;
    height: 2.5vw;
  }
  .tamaño_M{
    width:3vw;
    height:3vw;
  }
  .tamaño_L{
    width: 3.5vw;
    height: 3.5vw;
  }



  canvas{
    width: 50vw;
    height: 70vh;
    border: 6px solid orange;
    display:block;
  }
</style>
