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
      <h1>
        👋
        {{
          spanish
            ? "Hola, soy Wladimir Sanvicente"
            : "Hi, I'm Wladimir Sanvicente"
        }}
      </h1>
      <div style="padding: 1rem">
        <p v-show="spanish" style="font-size: 1.2rem">
          Soy <b>desarrollador frontend</b> con experiencia en <b>Vue.js</b>.
          Soy bueno en <b>CSS</b> y <b>HTML</b>, así como en
          <b>JavaScript.</b> Me encanta aprender cosas nuevas y experimentar con
          nuevas tecnologías. Tengo buen ojo para los detalles y siempre pongo
          todo de mi en mi trabajo.
        </p>
        <p v-show="!spanish" style="font-size: 1.2rem">
          I am a <b>frontend developer</b> with experience in <b>Vue.js</b>.
          I&apos;m good at <b>HTML</b> and <b>CSS</b>, as well as
          <b>JavaScript</b>. I love learning new things and experimenting with
          new technologies. I have a good eye for details and I always put my
          all into my work.
        </p>
      </div>
    </div>
  </div>
</template>