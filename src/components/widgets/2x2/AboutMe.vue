<script setup>
import { toRefs } from "vue";

const props = defineProps({
  spanish: Boolean,
});

const { spanish } = toRefs(props);
</script>
<template>
  <div
    class="home__container big"
    style="
      background-image: url('https://cdna.artstation.com/p/assets/images/images/021/720/920/original/pixel-jeff-mario.gif?1572709433');
      background-position: bottom;
    "
  >
    <div class="content">
      <div style="padding: 1rem;">
        <h1>
          {{
            spanish
            ? "Hola, soy Wladimir Sanvicente"
            : "Hi, I'm Wladimir Sanvicente"
          }}
          👋
        </h1>
      </div>
      <div style="padding: 1rem">
        <p v-show="spanish" style="font-size: 1.2rem">
          <b>Desarrollador Frontend</b> con experiencia en <b>Vue.js</b>, <b>CSS</b>, <b>HTML</b> y <b>JavaScript.</b> 
          Me gusta experimentar con proyectos nuevos, en especial con video juegos.
        </p>
        <p v-show="!spanish" style="font-size: 1.2rem">
          <b>Frontend developer</b> with experience in <b>Vue.js</b>, <b>HTML</b>, <b>CSS</b> and <b>JavaScript</b>. 
          I love experimenting with new projects, especially with video games.
        </p>
      </div>
    </div>
  </div>
</template>