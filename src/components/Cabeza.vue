<template>
  <v-stage
    ref="stage"
    :config="stageSize"
    @mousedown="handleStageMouseDown"
    @touchstart="handleStageMouseDown"
  >
    <v-layer ref="layer">
      <v-rect
        v-for="item in rectangles"
        :key="item.id"
        :config="item"
        @transformend="handleTransformEnd"
      />
      <v-transformer ref="transformer" />
    </v-layer>
  </v-stage>
</template>

<script>
import Konva from "konva";
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
      rectangles: [
        {
          rotation: 0,
          x: 10,
          y: 10,
          width: 100,
          height: 100,
          scaleX: 1,
          scaleY: 1,
          fill: "red",
          name: "rect1",
          draggable: true,
        },
      ],
      selectedShapeName: "",
    };
  },
  methods: {
    handleTransformEnd(e) {
      const rect = this.rectangles.find(
        (r) => r.name === this.selectedShapeName
      );

      rect.x = e.target.x();
      rect.y = e.target.y();
      rect.rotation = e.target.rotation();
      rect.scaleX = e.target.scaleX();
      rect.scaleY = e.target.scaleY();

      rect.fill = Konva.Util.getRandomColor();
    },
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
      const rect = this.rectangles.find((r) => r.name === name);
      if (rect) {
        this.selectedShapeName = name;
      } else {
        this.selectedShapeName = "";
      }
      this.updateTransformer();
    },
    updateTransformer() {
      const transformerNode = this.$refs.transformer.getNode();
      const stage = transformerNode.getStage();
      const { selectedShapeName } = this;

      const selectedNode = stage.findOne("." + selectedShapeName);

      if (selectedNode === transformerNode.node()) {
        return;
      }

      if (selectedNode) {
        transformerNode.nodes([selectedNode]);
      } else {
        transformerNode.nodes([]);
      }
      transformerNode.getLayer().batchDraw();
    },
  },
};
</script>
