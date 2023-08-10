<script setup>
import { toRefs, toHandlers } from "vue";

const props = defineProps({
  spanish: Boolean
});

const { spanish } = toRefs(props);
const emit = defineEmits(['changeLanguage']);

const handlerlanguage = ()=>{ emit('changeLanguage') }

</script>
<template>
  <div class="home__container small interactive language" @click="handlerlanguage">
      <h1 style="font-size: 2.5rem;">{{ spanish ? "ES" : "EN" }}</h1>
      <p style="display: flex; align-items: center; justify-content: center; gap: 0.8rem; font-size: 1.5rem; font-weight: 700;">
        <span :style="{ color: !spanish ? '#c084fc' : '' }">EN</span>
        <span :style="{ color: spanish ? '#c084fc' : '' }">ES</span>
      </p>
    </div>
</template>