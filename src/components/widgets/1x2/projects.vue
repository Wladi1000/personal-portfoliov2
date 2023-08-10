<script setup>
import { toRefs } from "vue";


const props = defineProps({
  spanish: Boolean
});

const { spanish } = toRefs(props);

// Cornifer State
let cornifer = new Audio("/cornifer.mp3");
</script>
<template>
  <div
    @mouseenter="cornifer.play()"
    @mouseleave="cornifer.pause()"
    style="
      background-image: url('https://media.tenor.com/DmC5jNLSQ0IAAAAC/cornifer.gif');
      background-size: cover;
      background-repeat: no-repeat;
      background-position: center;
    "
    class="home__container medium interactive"
  >
    <div class="content" v-show="spanish">
      <h1>Proyectos</h1>
      <p>Aquí puedes encontrar algunos de mis proyectos.</p>
    </div>
    <div class="content" v-show="!spanish">
      <h1>Projects</h1>
      <p>Here you can find some of my projects.</p>
    </div>
  </div>
</template>