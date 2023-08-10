<script setup>
import { toRefs } from "vue";

const props = defineProps({
  spanish: Boolean
});

const { spanish } = toRefs(props);

</script>
<template>
  <a
    class="home__container medium interactive"
    style="
      background-image: url('https://media.tenor.com/YZPnGuPeZv8AAAAd/coding.gif');
      background-size: cover;
      background-repeat: no-repeat;
      background-position: center;
    "
    href="https://github.com/Wladi1000"
    target="_blank"
    rel="noopener noreferrer"
  >
    <div class="content" v-show="spanish">
      <svg
        style="margin-right: 1rem; margin-top: 1rem"
        width="1rem"
        height="1rem"
        stroke="currentColor"
        fill="currentColor"
        stroke-width="0"
        viewBox="0 0 24 24"
        class="href-icon"
        xmlns="http://www.w3.org/2000/svg"
      >
        <path fill="none" d="M0 0h24v24H0z"></path>
        <path
          d="M19 19H5V5h7V3H5a2 2 0 00-2 2v14a2 2 0 002 2h14c1.1 0 2-.9 2-2v-7h-2v7zM14 3v2h3.59l-9.83 9.83 1.41 1.41L19 6.41V10h2V3h-7z"
        ></path>
      </svg>
      <h1>Github</h1>
      <p>Mi perfil de Github, donde subo mis proyectos.</p>
    </div>
    <div class="content" v-show="!spanish">
      <svg
        style="margin-right: 1rem; margin-top: 1rem"
        width="1rem"
        height="1rem"
        stroke="currentColor"
        fill="currentColor"
        stroke-width="0"
        viewBox="0 0 24 24"
        class="href-icon"
        xmlns="http://www.w3.org/2000/svg"
      >
        <path fill="none" d="M0 0h24v24H0z"></path>
        <path
          d="M19 19H5V5h7V3H5a2 2 0 00-2 2v14a2 2 0 002 2h14c1.1 0 2-.9 2-2v-7h-2v7zM14 3v2h3.59l-9.83 9.83 1.41 1.41L19 6.41V10h2V3h-7z"
        ></path>
      </svg>
      <h1>Github</h1>
      <p>My GitHub profile, where I upload my projects.</p>
    </div>
  </a>
</template>