<script setup>
import { toRefs } from "vue";

const props = defineProps({
  spanish: Boolean
});

const { spanish } = toRefs(props);

const experience = 4;
  
</script>
<template>
  <div class="home__container small" style="background-color: #0385ffbc">
    <div style="display: grid; place-items: center" v-show="spanish">
      <h1>+{{experience}}</h1>
      <p>AÑOS DE EXPERIENCIA</p>
    </div>
    <div style="display: grid; place-items: center" v-show="!spanish">
      <h1>+{{experience}}</h1>
      <p>YEARS OF EXPERIENCE</p>
    </div>
  </div>
</template>
