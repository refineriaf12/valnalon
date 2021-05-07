<template>
  <div class="home">
    <Header />
    <!-- <div id="app"> -->
      
      <!-- Canvas -->
      <!-- <canvas id="c"></canvas> -->
      <!-- Add Rectangle Button -->
      <!-- <div>
        <button @click="drawRect">Add Rect</button>
    <button @click="subWidth">-</button>
    <button @click="addWidth">+</button>
      </div>
    </div> -->
    <Cabeza />
    <!-- <Robot /> -->
    <Footer />
  </div>
</template>

<script>
// @ is an alias to /src
// import Robot from '@/components/Robot.vue'
import Header from "@/components/Header.vue";
import Footer from "@/components/Footer.vue";
import Cabeza from '@/components/Cabeza.vue'

export default {
  name: "Home",
  components: {
    Header,
    Footer,
    Cabeza
    
    
  },
}

//   data(){
//     return{
//       el : '#app',
      
//       vueCanvas: null,
//       rectWidth: 200

//     }
//   },
//   mounted() {
//     var c = document.getElementById("c");
//     var ctx = c.getContext("2d");
//     this.vueCanvas = ctx;
//   },
//   methods: {
//     drawRect() {
//       this.vueCanvas.clearRect(0, 0, 100, 200);//borrar
//       this.vueCanvas.beginPath();
//       this.vueCanvas.rect(20, 20, this.rectWidth, 100);
//       this.vueCanvas.stroke();
//     },
//     addWidth() {
//       this.rectWidth += 10
//       this.drawRect()
//     },
//     subWidth() {
//       this.rectWidth -= 10
//       this.drawRect()      
//     }
//   },
// };
</script>
<style scoped>
 /* #app {
   padding: 20px;
   margin: 20px;
 }

 #c {
   height: 200px;
   width: 400px;
   border: 1px solid gray;
 } */
 </style>
