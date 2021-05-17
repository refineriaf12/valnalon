<template>
  <div class="piezas">
    
    <v-stage
      class="lienzo"
      id="lienzo"
      ref="stage"
      :config="stageSize"
      @mousedown="handleStageMouseDown"
    >
      <v-layer ref="layer">
        <v-image v-for="item in images" :key="item.id" :config="item" />
        <v-transformer ref="transformer" />
      </v-layer>
    </v-stage>
    <button @click="descargaImagen">Descarga</button>
  </div>
</template>
<script>
const width = window.innerWidth;
const height = window.innerHeight;
export default {
  name: "piezas",
  data() {
    return {
      stageSize: {
        width: 400,
        height: 600,
      },
      images: [
        {
          image: null,
          x: 128,
          y: 320,
          width: 150,
          height: 260,
          name: "piernas",
          draggable: true,
        },
        {
          image: null,
          x: 122,
          y: 175,
          width: 160,
          height: 150,
          name: "torso",
          draggable: true,
        },
        {
          image: null,
          x: 250,
          y: 100,
          width: 30,
          height: 55,
          name: "orejaDer",
          draggable: true,
        },
        {
          image: null,
          x: 120,
          y: 100,
          width: 30,
          height: 55,
          name: "orejaIzq",
          draggable: true,
        },
        {
          image: null,
          x: 140,
          y: 50,
          width: 120,
          height: 135,
          name: "cabeza",
          draggable: true,
        },
        {
          image: null,
          x: 175,
          y: 240,
          width: 55,
          height: 55,
          name: "corazon",
          draggable: true,
        },
        {
          image: null,
          x: 175,
          y: 110,
          width: 50,
          height: 10,
          name: "ojos",
          draggable: true,
        },
        {
          image: null,
          x: 195,
          y: 120,
          width: 10,
          height: 15,
          name: "nariz",
          draggable: true,
        },
        {
          image: null,
          x: 184,
          y: 140,
          width: 35,
          height: 15,
          name: "boca",
          draggable: true,
        },
        {
          image: null,
          x: 262,
          y: 250,
          width: 55,
          height: 175,
          name: "brazoDer",
          draggable: true,
        },
        {
          image: null,
          x: 85,
          y: 250,
          width: 55,
          height: 175,
          name: "brazoIzq",
          draggable: true,
        },
        {
          image: null,
          x: 220,
          y: 540,
          width: 80,
          height: 40,
          name: "pieDer",
          draggable: true,
        },
        {
          image: null,
          x: 120,
          y: 550,
          width: 60,
          height: 30,
          name: "pieIzq",
          draggable: true,
        },
      ],
      selectedShapeName: "",
    };
  },
  created() {
    const piernas = new window.Image();
    piernas.src =
      "http://owncloud.valnalon.com/index.php/s/Oy6pcf3LEYr3BgM/download?path=%2FF5-ROBOT&files=piernas.png";
    piernas.onload = () => {
      this.images[0].image = piernas;
    };
    const torso = new window.Image();
    torso.src =
      "http://owncloud.valnalon.com/index.php/s/Oy6pcf3LEYr3BgM/download?path=%2FF5-ROBOT&files=torso.png";
    torso.onload = () => {
      this.images[1].image = torso;
    };
    const orejaDer = new window.Image();
    orejaDer.src =
      "http://owncloud.valnalon.com/index.php/s/Oy6pcf3LEYr3BgM/download?path=%2FF5-ROBOT&files=orejaDe.png";
    orejaDer.onload = () => {
      this.images[2].image = orejaDer;
    };
    const orejaIzq = new window.Image();
    orejaIzq.src =
      "http://owncloud.valnalon.com/index.php/s/Oy6pcf3LEYr3BgM/download?path=%2FF5-ROBOT&files=orejaIz.png";
    orejaIzq.onload = () => {
      this.images[3].image = orejaIzq;
    };
    const cabeza = new window.Image();
    cabeza.src =
      "http://owncloud.valnalon.com/index.php/s/Oy6pcf3LEYr3BgM/download?path=%2FF5-ROBOT&files=cabeza.png";
    cabeza.onload = () => {
      this.images[4].image = cabeza;
    };
    const corazon = new window.Image();
    corazon.src =
      "http://owncloud.valnalon.com/index.php/s/Oy6pcf3LEYr3BgM/download?path=%2FF5-ROBOT&files=corazon.png";
    corazon.onload = () => {
      this.images[5].image = corazon;
    };
    const ojos = new window.Image();
    ojos.src =
      "http://owncloud.valnalon.com/index.php/s/Oy6pcf3LEYr3BgM/download?path=%2FF5-ROBOT&files=ojos.png";
    ojos.onload = () => {
      this.images[6].image = ojos;
    };
    const nariz = new window.Image();
    nariz.src =
      "http://owncloud.valnalon.com/index.php/s/Oy6pcf3LEYr3BgM/download?path=%2FF5-ROBOT&files=nariz.png";
    nariz.onload = () => {
      this.images[7].image = nariz;
    };
    const boca = new window.Image();
    boca.src =
      "http://owncloud.valnalon.com/index.php/s/Oy6pcf3LEYr3BgM/download?path=%2FF5-ROBOT&files=boca.png";
    boca.onload = () => {
      this.images[8].image = boca;
    };
    const brazoDer = new window.Image();
    brazoDer.src =
      "http://owncloud.valnalon.com/index.php/s/Oy6pcf3LEYr3BgM/download?path=%2FF5-ROBOT&files=brazoDe.png";
    brazoDer.onload = () => {
      this.images[9].image = brazoDer;
    };
    const brazoIzq = new window.Image();
    brazoIzq.src =
      "http://owncloud.valnalon.com/index.php/s/Oy6pcf3LEYr3BgM/download?path=%2FF5-ROBOT&files=brazoIz.png";
    brazoIzq.onload = () => {
      this.images[10].image = brazoIzq;
    };
    const pieDer = new window.Image();
    pieDer.src =
      "http://owncloud.valnalon.com/index.php/s/Oy6pcf3LEYr3BgM/download?path=%2FF5-ROBOT&files=pieDe.png";
    pieDer.onload = () => {
      this.images[11].image = pieDer;
    };
    const pieIzq = new window.Image();
    pieIzq.src =
      "http://owncloud.valnalon.com/index.php/s/Oy6pcf3LEYr3BgM/download?path=%2FF5-ROBOT&files=pieIz.png";
    pieIzq.onload = () => {
      this.images[12].image = pieIzq;
    };
  },
  methods: {
    handleStageMouseDown(e) {
      if (e.target === e.target.getStage()) {
        this.selectedShapeName = "";
        this.updateTransformer();
        return;
      }

      const clickedOnTransformer =
        e.target.getParent().className === "Transformer";
      if (clickedOnTransformer) {
        return;
      }

      const name = e.target.name();
      const img = this.images.find((r) => r.name === name);
      if (img) {
        this.selectedShapeName = name;
      } else {
        this.selectedShapeName = "";
      }
      this.updateTransformer();
    },
    updateTransformer() {
      const transformerNode = this.$refs.transformer.getStage();
      const stage = transformerNode.getStage();
      const { selectedShapeName } = this;

      const selectedNode = stage.findOne("." + selectedShapeName);

      if (selectedNode === transformerNode.node()) {
        return;
      }

      if (selectedNode) {
        transformerNode.attachTo(selectedNode);
      } else {
        transformerNode.detach();
      }
      transformerNode.getLayer().batchDraw();
    },
    guardaImagen(uri, name) {
      var link = document.createElement("a");
      link.download = name;
      link.href = uri;
      document.body.appendChild(link);
      link.click();
      document.body.removeChild(link);
      // delete link;
    },
    descargaImagen() {
      var dataURL = stage.toDataURL({ pixelRatio: 3 });
      this.guardaImagen(dataURL, "stage.png");
    },
  },
};
</script>
<style scoped>
.piezas {
  display: flex;
  justify-content: center;
}
.lienzo {
  width: 410px;
  height: 600px;
  border: 5px solid orange;
}
</style>
