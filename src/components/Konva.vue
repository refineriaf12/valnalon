<template>
  <div id="app">
    <v-stage ref="stage" :config="stageSize" @mousedown="handleStageMouseDown">
      <v-layer ref="layer">
        <v-group ref="imageGroup">
          <v-image
            :config="{
              image: ojos,
              x: 150,
              y: 150,
              draggable: true,
            }"
          />
          <v-image
            :config="{
              image: orejaIzq,
              x: 80,
              y: 80,
              draggable: true,
            }"
          />
          <v-image
            :config="{
              image: piernas,
              x: 280,
              y: 280,
              draggable: true,
            }"
          />
          -->
        </v-group>
        <v-transformer ref="transformer" />
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
      stageSize: {
        width: width,
        height: height,
      },

      nariz: [
        {
          rotation: 0,

          width: 100,
          height: 100,
          scaleX: 1,
          scaleY: 1,
          fill: "red",
          name: "image1",
          draggable: true,
        },
      ],

      nariz: null,
      selectedShapeName: "",
      ojos: null,
      orejaIzq: null,
      piernas:null,
      selectedNode: null,
      imageGroup: null,
      transformer: null,
      stage: null
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

  mounted() {
    this.transformer = this.$refs.transformer.getStage();
    this.imageGroup = this.$refs.imageGroup.getStage();
    this.stage = this.$refs.stage.getStage();
    
  },

  methods: {
    handleTransformEnd(e) {
      const image = this.nariz.find((r) => r.name === this.selectedShapeName);

      image.x = e.target.x();
      image.y = e.target.y();
      image.rotation = e.target.rotation();
      image.scaleX = e.target.scaleX();
      image.scaleY = e.target.scaleY();

      image.fill = Konva.Util.getRandomColor();
    },
    handleStageMouseDown(e) {
      if (e.target === e.target.getStage()) {
        this.selectedImageName = "";
        this.selectedNode = null;
        this.updateTransformer();
        return;
      }

      const clickedOnTransformer =
        e.target.getParent().className === "Transformer";
      if (clickedOnTransformer) {
        return;
      }

      const name = e.target.name();
      const image = this.nariz.find((r) => r.name === name);
      if (image) {
        this.selectedImageName = name;
        this.selectedNode = this.imageGroup.find(
          ".".concat(this.selectedImageName)
        )[0];
        this.selectedNode.moveToTop();
      } 
      this.updateTransformer();
    },
    updateTransformer() {
      const transformerNode = this.transformer;
      if (this.cropMode) {
        transformerNode.detach();
      } else if (this.selectedNode === transformerNode.node()) {
        // do nothing if selected node is already attached
        return;
      } else if (this.selectedNode) {
        // attach to another node
        this.selectedNode.moveToTop();
        transformerNode.attachTo(this.selectedNode);
      } else {
        // remove transformer
        transformerNode.detach();
      }
      transformerNode.getLayer().batchDraw();
    },
    },
  
};
</script>
