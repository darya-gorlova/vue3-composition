<template>
  <div class="container">
    <div
      class="small-box"
      v-for="box in boxes"
      :key="box.id"
      :class="box.color"
      @click="changeColor(box.color)"
      @mouseover="onHover(box.id)"
    ></div>
  </div>
  <!-- display color here -->
  <div class="box"></div>
</template>

<script>
import { defineComponent, ref } from "vue";
export default defineComponent({
  name: "DisplayColorOnHoverComp",
  setup() {
    const boxes = ref([
      {
        id: 0,
        color: "red",
      },
      {
        id: 1,
        color: "yellow",
      },
      {
        id: 2,
        color: "blue",
      },
    ]);

    // 1.example with dynamic css value binding
    let color = ref("green");
    function changeColor(colour) {
      color.value = colour;
    }
    // 2.example
    let selected = ref(0);
    function onHover(id) {
      selected = id;
      color.value = boxes.value[selected].color;
    }

    return { boxes, color, changeColor, onHover };
  },
});
</script>
<style scoped>
.container {
  display: flex;
}
.small-box {
  width: 20px;
  height: 20px;
  border: solid;
  margin: 20px;
}

.box {
  /* how to bind value dynamically */
  background-color: v-bind(color);
  width: 200px;
  height: 200px;
}

.red {
  background-color: red;
}
.yellow {
  background-color: yellow;
}
.blue {
  background-color: blue;
}
</style>
