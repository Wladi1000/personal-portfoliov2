<script setup>
import languageSwicht from "../components/widgets/1x1/languageSwicht.vue";
import themeSwith from "../components/widgets/1x1/themeSwith.vue";
import Age from "../components/widgets/1x1/age.vue";
import linkedn from "../components/widgets/1x1/linkedn.vue";
import Skills from "../components/widgets/1x1/skills.vue";
import Experience from "../components/widgets/1x1/experience.vue";
import Discord from "../components/widgets/1x1/discord.vue";
import Mailto from "../components/widgets/1x1/mailto.vue";
import Projects from "../components/widgets/1x2/projects.vue";
import Github from "../components/widgets/1x2/github.vue";
import Spotify from "../components/widgets/1x2/spotify.vue";
import AboutMe from "../components/widgets/2x2/AboutMe.vue";

import { ref } from "vue";

// Language State
let spanish = ref(false);

const handlerlanguage = () => {
  spanish.value = !spanish.value;
  return;
};

</script>
<template>
  <section class="home">
    <!-- About -->
    <AboutMe :spanish="spanish"/>
    <!-- Language -->
    <languageSwicht :spanish="spanish" @change-language="handlerlanguage" />
    <!-- DarkMode toggle -->
    <themeSwith/>
    <!-- Age -->
    <Age :spanish="spanish" />
    <!-- Linkedn -->
    <linkedn/>
    <!-- Projects -->
    <Projects :spanish="spanish" /> 
    <!-- Github -->
    <Github :spanish="spanish"/>
    <!-- Skills -->
    <Skills/>
    <!-- Years Experience -->
    <Experience :spanish="spanish"/>
    <!-- Spotify -->
    <Spotify :spanish="spanish" />
    <!-- Discord -->
    <Discord />
    <!-- mailto -->
    <Mailto/>
  </section>
</template>