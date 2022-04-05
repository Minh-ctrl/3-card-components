<script>
import { ref } from "vue";
import TestComponent from "./components/TestComponent.vue";
import Data from "./components/Data";
export default {
  name: "App",
  components: {
    TestComponent,
  },
  setup() {
    const carsInfo = ref(Data);
    return { carsInfo };
  },
};
</script>
<template>
  <div class="container">
  <TestComponent :cars="carsInfo" />
  </div>
</template>

<style>
@import "./assets/base.css";
.container {
  display: flex;
  flex-flow: row wrap;
}
.orange {
  background-color: hsl(31, 77%, 52%);
}
.cyan {
  background-color: hsl(184, 100%, 22%);
}
.dark-cyan {
  background-color: hsl(179, 100%, 13%);
}
</style>
