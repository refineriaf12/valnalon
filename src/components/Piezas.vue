<template>
  <div class="piezas">
    <v-stage ref="stage" :config="stageSize" @mousedown="handleStageMouseDown">
      <v-layer ref="layer">
        <v-image v-for="item in images" :key="item.id" :config="item" />
        <v-transformer ref="transformer" />
      </v-layer>
    </v-stage>
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
        width: width,
        height: height,
      },
      images: [
        {
          image: null,
          x: 150,
          y: 100,
          width: 20,
          height: 20,
          name: "nariz",
          draggable: true,
        },
        {
          image: null,
          x: 150,
          y: 80,
          width: 20,
          height: 20,
          name: "ojos",
          draggable: true,
        },
        {
          image: null,
          x: 100,
          y: 65,
          width: 35,
          height: 35,
          name: "orejaIzq",
          draggable: true,
        },
        {
          image: null,
          x: 105,
          y: 155,
          width: 85,
          height: 150,
          name: "pierna",
          draggable: true,
        },
      ],
      selectedShapeName: "",
    };
  },
  created() {
      const nariz = new window.Image();
      nariz.src =
        "https://gist.githubusercontent.com/diazgjulian/94101cb9314f60c705c4b6beb06fce6e/raw/e3224f65be86ee400f95130b44cbc79a813fad82/nariz.svg";
      nariz.onload = () => {
        this.images[0].image = nariz;
      };
    const ojos = new window.Image();
    ojos.src =
      "https://gist.githubusercontent.com/diazgjulian/94101cb9314f60c705c4b6beb06fce6e/raw/e3224f65be86ee400f95130b44cbc79a813fad82/ojos.svg";
    ojos.onload = () => {
      this.images[1].image = ojos;
    };
    const orejaIzq = new window.Image();
    orejaIzq.src =
      "https://gist.githubusercontent.com/diazgjulian/94101cb9314f60c705c4b6beb06fce6e/raw/e3224f65be86ee400f95130b44cbc79a813fad82/orejaIz.svg";
    orejaIzq.onload = () => {
      this.images[2].image = orejaIzq;
    };
    const pierna = new window.Image();
    pierna.src =
      "https://gist.githubusercontent.com/diazgjulian/94101cb9314f60c705c4b6beb06fce6e/raw/e3224f65be86ee400f95130b44cbc79a813fad82/piernas.svg";
    pierna.onload = () => {
      this.images[3].image = pierna;
    };
  },
  methods: {
    handleStageMouseDown(e) {
      // clicked on stage - cler selection
      if (e.target === e.target.getStage()) {
        this.selectedShapeName = "";
        this.updateTransformer();
        return;
      }

      // clicked on transformer - do nothing
      const clickedOnTransformer =
        e.target.getParent().className === "Transformer";
      if (clickedOnTransformer) {
        return;
      }

      // find clicked img by its name
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
      // here we need to manually attach or detach Transformer node
      const transformerNode = this.$refs.transformer.getStage();
      const stage = transformerNode.getStage();
      const { selectedShapeName } = this;

      const selectedNode = stage.findOne("." + selectedShapeName);
      // do nothing if selected node is already attached
      if (selectedNode === transformerNode.node()) {
        return;
      }

      if (selectedNode) {
        // attach to another node
        transformerNode.attachTo(selectedNode);
      } else {
        // remove transformer
        transformerNode.detach();
      }
      transformerNode.getLayer().batchDraw();
    },
  },
};
</script>
