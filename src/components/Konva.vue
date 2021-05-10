<template>
  <div id="app">
    <img :src="image" />
    <v-stage ref="stage" :config="stageSize">
      <v-layer ref="layer">
        <!-- <v-image
         
            :config="{
            image: image,
            x: 150,
            y: 150,
            draggable: true,
                      }"/> -->
      </v-layer>
    </v-stage>
  </div>
</template>
<script>
import image from "@/assets/logo.png";
const width = window.innerWidth;
const height = window.innerHeight;


export default {
  name: "app",
  data() {
    return {
      image: image,
      stageSize: {
        width: width,
        height: height,
       
       
      },

      isDragging: false,
      image: image,
    };
  },
  created() {
    const imageObj = new window.Image();
    imageObj.src = "../assets/logo.png";
    imageObj.onload = () => {
      
      this.imageObj = image;
    };
    
  },

  methods: {
    handleDragStart() {
      this.isDragging = true;
    },
    handleDragEnd() {
      this.isDragging = false;
    },
  },
};
</script>
