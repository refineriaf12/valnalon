<template>
  <div id="app">
    <v-stage ref="stage" :config="canvas">
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
        <v-image
          @dragstart="handleDragStart"
          @dragend="handleDragEnd"
          :config="{
            image: ojos,
            x: 150,
            y: 150,
            draggable: true,
          }"
        />
        <v-image
          @dragstart="handleDragStart"
          @dragend="handleDragEnd"
          :config="{
            image: orejaIzq,
            x: 80,
            y: 80,
            draggable: true,
          }"
        />
        <v-image
          @dragstart="handleDragStart"
          @dragend="handleDragEnd"
          :config="{
            image: piernas,
            x: 280,
            y: 280,
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
      ojos: null,
      orejaIzq: null,
      piernas:null,
    };
  },
  created() {
    const nariz = new window.Image();
    nariz.src =
      "https://gist.githubusercontent.com/diazgjulian/94101cb9314f60c705c4b6beb06fce6e/raw/e3224f65be86ee400f95130b44cbc79a813fad82/nariz.svg";
    nariz.onload = () => {
      this.nariz = nariz;
    };

    const ojos = new window.Image();
    ojos.src =
      "https://gist.githubusercontent.com/diazgjulian/94101cb9314f60c705c4b6beb06fce6e/raw/e3224f65be86ee400f95130b44cbc79a813fad82/ojos.svg";
    ojos.onload = () => {
      this.ojos = ojos;
    };
    const orejaIzq = new window.Image();
    orejaIzq.src =
      "https://gist.githubusercontent.com/diazgjulian/94101cb9314f60c705c4b6beb06fce6e/raw/e3224f65be86ee400f95130b44cbc79a813fad82/orejaIz.svg";
    orejaIzq.onload = () => {
      this.orejaIzq = orejaIzq;
    };
    const piernas = new window.Image();
    piernas.src =
      "https://gist.githubusercontent.com/diazgjulian/94101cb9314f60c705c4b6beb06fce6e/raw/e3224f65be86ee400f95130b44cbc79a813fad82/piernas.svg";
    piernas.onload = () => {
      this.piernas = piernas;
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
<style scoped></style>
