<template>
  <div id="app">
    <h2>1. Change color of list element to red on hover</h2>
    <UnsortedListComp />
    <h2>2. Change color of big box to color of small box on hover</h2>
    <DisplayColorOnHoverComp />
  </div>
</template>

<script>
import { defineComponent } from "vue";
import UnsortedListComp from "./components/UnsortedListComp.vue";
import DisplayColorOnHoverComp from "./components/DisplayColorOnHoverComp.vue";
export default defineComponent({
  name: "App",
  components: { UnsortedListComp, DisplayColorOnHoverComp },
});
</script>

<style></style>
