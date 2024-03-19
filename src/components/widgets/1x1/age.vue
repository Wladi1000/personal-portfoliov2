<script setup>
import { toRefs } from "vue";


const props = defineProps({
  spanish: Boolean
});

const { spanish } = toRefs(props);

</script>
<template>
  <div class="home__container small" style="background-color: #299e3abc">
      <div style="display: grid; place-items: center" v-show="spanish">
        <p>EDAD</p>
        <h1>24</h1>
        <p>AÑOS</p>
      </div>
      <div style="display: grid; place-items: center" v-show="!spanish">
        <p>AGE</p>
        <h1>24</h1>
        <p>YEARS</p><p>OLD</p>
      </div>
    </div>
</template>
