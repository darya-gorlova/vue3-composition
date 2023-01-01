<template>
  <ul>
    <li
      class="list-element"
      v-for="fruit in fruits"
      :key="fruit"
      @mouseover="isHovering = true"
      @mouseout="isHovering = false"
    >
      {{ fruit }}
    </li>
  </ul>
</template>

<script>
import { defineComponent, ref } from "vue";
export default defineComponent({
  name: "UnsrotedListComp",
  setup() {
    const fruits = ref(["apple", "kiwi", "orange"]);
    const isHovering = ref(false);
    return { fruits, isHovering };
  },
});
</script>
<style scoped>
.list-element:hover {
  color: red;
}
</style>
