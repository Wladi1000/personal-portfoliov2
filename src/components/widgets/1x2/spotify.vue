<script setup>
import { reactive, onMounted, toRefs } from "vue";

const props = defineProps({
  spanish: Boolean
});
const { spanish } = toRefs(props);

// Spotify State
const spotifyState = reactive({
  album_art_url: "",
  artist: "",
  song: "",
  album: "",
  track_id: "",
});

const spotifySongRute = "https://open.spotify.com/intl-es/track/";

onMounted(() => {
  setInterval(async () => {
    const { data } = await fetch(
      "https://api.lanyard.rest/v1/users/201072569342885899"
    ).then((res) => res.json());

    // Spotify Setup
    if (data.spotify != null) {
      const keys = Object.keys(spotifyState);
      keys.forEach((key) => {
        spotifyState[key] = data.spotify[key];
      });
    }
  }, 250);
});
</script>
<template>
  <a
    class="home__container medium interactive"
    :href="spotifySongRute + spotifyState.track_id"
    target="_blank"
    rel="noopener noreferrer"
    :style="{ backgroundImage: 'url(' + spotifyState.album_art_url + ')' }"
    style="
      background-size: cover;
      background-repeat: no-repeat;
      background-position: center;
    "
  >
    <div class="content" v-if="spotifyState.song && spanish">
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
      <h1>¡Escuchando ahora mismo!</h1>
      <p style="font-weight: 700">{{ spotifyState.song }}</p>
      <p>{{ spotifyState.artist }}</p>
      <svg
        style="display: none"
        class="small__icon"
        stroke="currentColor"
        fill="currentColor"
        stroke-width="0"
        viewBox="0 0 16 16"
        height="1em"
        width="1em"
        xmlns="http://www.w3.org/2000/svg"
      >
        <path
          d="M8 0a8 8 0 1 0 0 16A8 8 0 0 0 8 0zm3.669 11.538a.498.498 0 0 1-.686.165c-1.879-1.147-4.243-1.407-7.028-.77a.499.499 0 0 1-.222-.973c3.048-.696 5.662-.397 7.77.892a.5.5 0 0 1 .166.686zm.979-2.178a.624.624 0 0 1-.858.205c-2.15-1.321-5.428-1.704-7.972-.932a.625.625 0 0 1-.362-1.194c2.905-.881 6.517-.454 8.986 1.063a.624.624 0 0 1 .206.858zm.084-2.268C10.154 5.56 5.9 5.419 3.438 6.166a.748.748 0 1 1-.434-1.432c2.825-.857 7.523-.692 10.492 1.07a.747.747 0 1 1-.764 1.288z"
        ></path>
      </svg>
    </div>
    <div class="content" v-else-if="spotifyState.song && !spanish">
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
      <h1>Listening Right Now!</h1>
      <p style="font-weight: 700">{{ spotifyState.song }}</p>
      <p>{{ spotifyState.artist }}</p>
      <svg
        style="display: none"
        class="small__icon"
        stroke="currentColor"
        fill="currentColor"
        stroke-width="0"
        viewBox="0 0 16 16"
        height="1em"
        width="1em"
        xmlns="http://www.w3.org/2000/svg"
      >
        <path
          d="M8 0a8 8 0 1 0 0 16A8 8 0 0 0 8 0zm3.669 11.538a.498.498 0 0 1-.686.165c-1.879-1.147-4.243-1.407-7.028-.77a.499.499 0 0 1-.222-.973c3.048-.696 5.662-.397 7.77.892a.5.5 0 0 1 .166.686zm.979-2.178a.624.624 0 0 1-.858.205c-2.15-1.321-5.428-1.704-7.972-.932a.625.625 0 0 1-.362-1.194c2.905-.881 6.517-.454 8.986 1.063a.624.624 0 0 1 .206.858zm.084-2.268C10.154 5.56 5.9 5.419 3.438 6.166a.748.748 0 1 1-.434-1.432c2.825-.857 7.523-.692 10.492 1.07a.747.747 0 1 1-.764 1.288z"
        ></path>
      </svg>
    </div>
    <div class="content" v-else-if="!spotifyState.song && spanish">
      <h1>Desconectado</h1>
      <svg
        style="
          height: 100%;
          width: 30%;
          padding: 5%;
          opacity: 0.2;
          align-self: center;
        "
        class="small__icon"
        stroke="currentColor"
        fill="currentColor"
        stroke-width="0"
        viewBox="0 0 16 16"
        height="1em"
        width="1em"
        xmlns="http://www.w3.org/2000/svg"
      >
        <path
          d="M8 0a8 8 0 1 0 0 16A8 8 0 0 0 8 0zm3.669 11.538a.498.498 0 0 1-.686.165c-1.879-1.147-4.243-1.407-7.028-.77a.499.499 0 0 1-.222-.973c3.048-.696 5.662-.397 7.77.892a.5.5 0 0 1 .166.686zm.979-2.178a.624.624 0 0 1-.858.205c-2.15-1.321-5.428-1.704-7.972-.932a.625.625 0 0 1-.362-1.194c2.905-.881 6.517-.454 8.986 1.063a.624.624 0 0 1 .206.858zm.084-2.268C10.154 5.56 5.9 5.419 3.438 6.166a.748.748 0 1 1-.434-1.432c2.825-.857 7.523-.692 10.492 1.07a.747.747 0 1 1-.764 1.288z"
        ></path>
      </svg>
    </div>
    <div class="content" v-else>
      <h1>Taking a break</h1>
      <svg
        style="
          height: 100%;
          width: 30%;
          padding: 5%;
          opacity: 0.2;
          align-self: center;
        "
        class="small__icon"
        stroke="currentColor"
        fill="currentColor"
        stroke-width="0"
        viewBox="0 0 16 16"
        height="1em"
        width="1em"
        xmlns="http://www.w3.org/2000/svg"
      >
        <path
          d="M8 0a8 8 0 1 0 0 16A8 8 0 0 0 8 0zm3.669 11.538a.498.498 0 0 1-.686.165c-1.879-1.147-4.243-1.407-7.028-.77a.499.499 0 0 1-.222-.973c3.048-.696 5.662-.397 7.77.892a.5.5 0 0 1 .166.686zm.979-2.178a.624.624 0 0 1-.858.205c-2.15-1.321-5.428-1.704-7.972-.932a.625.625 0 0 1-.362-1.194c2.905-.881 6.517-.454 8.986 1.063a.624.624 0 0 1 .206.858zm.084-2.268C10.154 5.56 5.9 5.419 3.438 6.166a.748.748 0 1 1-.434-1.432c2.825-.857 7.523-.692 10.492 1.07a.747.747 0 1 1-.764 1.288z"
        ></path>
      </svg>
    </div>
  </a>
</template>