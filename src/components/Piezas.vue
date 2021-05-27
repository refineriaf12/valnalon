<template>
  <div class="piezas">
    <v-stage
      class="lienzo"
      id="lienzo"
      ref="stage"
      :config="stageSize"
      @mousedown="handleStageMouseDown"
    >
      <v-layer class="prueba" ref="layer">
        <v-image v-for="item in images" :key="item.id" :config="item" />
        <v-transformer ref="transformer" />
      </v-layer>
    </v-stage>
    <section class="guardar">
      <button class= "relleno" @click="descargaImagen">Descarga Tu Robot</button>
    </section>
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
        width: 550,
        height: 750,
      },
      images: [
        {
          image: null,
          x: 200,
          y: 390,
          width: 150,
          height: 260,
          name: "piernas",
          draggable: true,
        },
        {
          image: null,
          x: 194,
          y: 245,
          width: 160,
          height: 150,
          name: "torso",
          draggable: true,
        },
        {
          image: null,
          x: 322,
          y: 170,
          width: 30,
          height: 55,
          name: "orejaDer",
          draggable: true,
        },
        {
          image: null,
          x: 192,
          y: 170,
          width: 30,
          height: 55,
          name: "orejaIzq",
          draggable: true,
        },
        {
          image: null,
          x: 212,
          y: 120,
          width: 120,
          height: 135,
          name: "cabeza",
          draggable: true,
        },
        {
          image: null,
          x: 245,
          y: 310,
          width: 55,
          height: 55,
          name: "corazon",
          draggable: true,
        },
        {
          image: null,
          x: 247,
          y: 180,
          width: 50,
          height: 10,
          name: "ojos",
          draggable: true,
        },
        {
          image: null,
          x: 267,
          y: 190,
          width: 10,
          height: 15,
          name: "nariz",
          draggable: true,
        },
        {
          image: null,
          x: 254,
          y: 210,
          width: 35,
          height: 15,
          name: "boca",
          draggable: true,
        },
        {
          image: null,
          x: 334,
          y: 320,
          width: 55,
          height: 175,
          name: "brazoDer",
          draggable: true,
        },
        {
          image: null,
          x: 157,
          y: 320,
          width: 55,
          height: 175,
          name: "brazoIzq",
          draggable: true,
        },
        {
          image: null,
          x: 294,
          y: 610,
          width: 80,
          height: 40,
          name: "pieDer",
          draggable: true,
        },
        {
          image: null,
          x: 196,
          y: 620,
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
    piernas.crossOrigin = "Anonymous";
    piernas.src = "https://i.imgur.com/4rCp93y.png";
    piernas.onload = () => {
      this.images[0].image = piernas;
    };
    const torso = new window.Image();
    torso.crossOrigin = "Anonymous";
    torso.src = "https://i.imgur.com/VPJBSr3.png";
    torso.onload = () => {
      this.images[1].image = torso;
    };
    const orejaDer = new window.Image();
    orejaDer.crossOrigin = "Anonymous";
    orejaDer.src = "https://i.imgur.com/nakSnd8.png";
    orejaDer.onload = () => {
      this.images[2].image = orejaDer;
    };
    const orejaIzq = new window.Image();
    orejaIzq.crossOrigin = "Anonymous";
    orejaIzq.src = "https://i.imgur.com/Rj8Gke4.png";
    orejaIzq.onload = () => {
      this.images[3].image = orejaIzq;
    };
    const cabeza = new window.Image();
    cabeza.crossOrigin = "Anonymous";
    cabeza.src = "https://i.imgur.com/fiyDojQ.png";
    cabeza.onload = () => {
      this.images[4].image = cabeza;
    };
    const corazon = new window.Image();
    corazon.crossOrigin = "Anonymous";
    corazon.src = "https://i.imgur.com/GaHwz1W.png";
    corazon.onload = () => {
      this.images[5].image = corazon;
    };
    const ojos = new window.Image();
    ojos.crossOrigin = "Anonymous";
    ojos.src = "https://i.imgur.com/83eY2d1.png";
    ojos.onload = () => {
      this.images[6].image = ojos;
    };
    const nariz = new window.Image();
    nariz.crossOrigin = "Anonymous";
    nariz.src = "https://i.imgur.com/Zp3k8pK.png";
    nariz.onload = () => {
      this.images[7].image = nariz;
    };
    const boca = new window.Image();
    boca.crossOrigin = "Anonymous";
    boca.src = "https://i.imgur.com/N5zYgcN.png";
    boca.onload = () => {
      this.images[8].image = boca;
    };
    const brazoDer = new window.Image();
    brazoDer.crossOrigin = "Anonymous";
    brazoDer.src = "https://i.imgur.com/yscWc0m.png";
    brazoDer.onload = () => {
      this.images[9].image = brazoDer;
    };
    const brazoIzq = new window.Image();
    brazoIzq.crossOrigin = "Anonymous";
    brazoIzq.src = "https://i.imgur.com/0X2BZQF.png";
    brazoIzq.onload = () => {
      this.images[10].image = brazoIzq;
    };
    const pieDer = new window.Image();
    pieDer.crossOrigin = "Anonymous";
    pieDer.src = "https://i.imgur.com/nL071ua.png";
    pieDer.onload = () => {
      this.images[11].image = pieDer;
    };
    const pieIzq = new window.Image();
    pieIzq.crossOrigin = "Anonymous";
    pieIzq.src = "https://i.imgur.com/AqXNWM1.png";
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
     
    },
    descargaImagen() {
      const stage = this.$refs.stage.getStage();
      var dataURL = stage.toDataURL({ pixelRatio: 3 });
      this.guardaImagen(dataURL, "MiRobot.png");
    },
  },
};
</script>
<style scoped>
.lienzo {
  width: 560px;
  height: 760px;
  border: 5px solid #9e51ff;
 
}
.guardar {
  display: flex;
  align-items: center;
  justify-content: center;
  margin-top: 20px;
 
}
.relleno:hover,
.relleno:focus {
  box-shadow: inset 0 0 0 2em var(--hover);
}
.relleno {
  --color: #a972cb;
  --hover: #9e51ff;
}
button {
  color: var(--color);
  border: 5px solid #9e51ff;
  background-color: white;
  transition: 0.25s;
  padding: 1em 2em;
  box-shadow: 1px 12px 31px rgba(0, 0, 0, 0.5);
  
}
button:hover, button:focus {
  border-color: var(--hover);
  color: white;
}
</style>
