<style scoped>
#box-stage {
  border: 2px solid red;
  overflow: auto;
  height: 100%;
  width: 100%;
}
</style>

<template>
  <div id="box-stage">
    <div id="stage">hai</div>
  </div>
</template>

<script>
import Konva from "konva";

export default {
  data() {
    return {
      stage: {
        config: {
          container: "stage",
          width: 500,
          height: 500
        }
      }
    };
  },
  mounted() {
    this.initStage();
  },
  methods: {
    initStage() {
      var stage = new Konva.Stage(this.stage.config);
      var layer = new Konva.Layer();
      stage.add(layer);

      var circle = new Konva.Circle({
        x: stage.width() / 2,
        y: stage.height() / 2,
        radius: 50,
        fill: "green",
        draggable: true,
      });
      layer.add(circle);

      layer.draw();
    }
  }
};
</script>
