<script>
import IconSUVs from "./icons/IconSUVs.vue";
import IconSedans from "./icons/IconSedans.vue";
import IconLuxury from "./icons/IconLuxury.vue";
import { ref } from "vue";
// const sedans = ref("sedan");
// const suv = ref("suv");
// const luxuryClass = ref(true);
// const activeClass = ref('active')
export default {
  name: "TestComponent",
  components: {
    IconLuxury,
    IconSUVs,
    IconSedans,
  },
  props: {
    cars: {
      type: Array,
      required: true,
    },
  },
};
</script>
<template>
  <div class="wrapper">
    <div
      v-for="car in cars"
      class="static-wrapper"
      v-bind:key="car"
      :class="[{ luxury: car.luxury }, { sedan: car.sedan }, { suv: car.suv }]"
    >
      <IconLuxury v-if="car.type === 'LUXURY'" />
      <IconSUVs v-if="car.type === 'SUVS'" />
      <IconSedans v-if="car.type === 'SEDAN'" />
      <h1 class="title">{{ car.type }}</h1>
      <p class="description">{{ car.content }}</p>
    </div>
  </div>
</template>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Big+Shoulders+Display:wght@700&family=Lexend+Deca&display=swap");

.wrapper {
  height: fit-content;
  width: fit-content;
  max-height: 300px;
  max-width: 500px;
  border-color: beige;
  justify-content: center;
  align-items: center;
}
.static-wrapper {
  margin: 2rem 1.5rem 1.5rem 1.5rem;
  border-radius: 3%;
}
.title {
  margin: 0rem 1.5rem 1.5rem 1.5rem;
  align-self: flex-start;
  color: hsla(0, 0%, 100%, 0.89);
  font-weight: 400;
  letter-spacing: -0.1rem;
}
.sedan {
  background-color: hsl(31, 77%, 52%);
}
.luxury {
  background-color: hsl(184, 100%, 22%);
}

.suv{
  background-color: hsl(179, 100%, 13%);

}
.description {
  /* padding: 1rem; */
  margin: 1rem;
  color: var(--text-color);
  font-family: "Lexend Deca", sans-serif;
}
</style>
