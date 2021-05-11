<template>
  <div id="app">
    <v-stage ref="stage"   :config="canvas">
      <v-layer ref="layer">
        <v-image
          @dragstart="handleDragStart"
          @dragend="handleDragEnd"
          :config="{
            image: nariz,
            x: 50,
            y: 50,
            draggable: true,
          }"
        />
      </v-layer>
    </v-stage>
    
  </div>
</template>
<script>
const width = window.innerWidth;
const height = window.innerHeight;

export default {
  name: "app",
  data() {
    return {
      canvas: {
        width: width,
        height: height,
        
      },
      nariz: null,
    };
  },
  created() {
    const nariz= new window.Image();
    nariz.src =
      "https://gist.githubusercontent.com/diazgjulian/94101cb9314f60c705c4b6beb06fce6e/raw/e3224f65be86ee400f95130b44cbc79a813fad82/nariz.svg";
    nariz.onload = () => {
      this.nariz = nariz;
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
<style scoped>
canvas {
  border: 6px solid orange;
  display: block;
}
</style>
