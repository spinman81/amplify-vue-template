<script setup>
import { ref } from "vue";
import { NButton, NInput, NInputGroup, NDivider, NFlex } from "naive-ui";
import VideoPlayer from "./components/VideoPlayer.vue";

const url = ref("https://195181171156.cdn.etvnet.com/vod/AsnsW1TP0hmKuVms8dub3wKtM3Iyh90HsMcXNp6K7bplWcjZylGlmMicvGA6svLtkew3sxpcd_SHJfvtsc_VgQ/playlist.m3u8");
const playerOptions = {
  autoplay: false,
  controls: true,
  muted: true,
  width: 960,
  sources: [
    {
      src: url.value,
      type: "application/x-mpegURL",
    },
  ],
};
</script>

<template>
    <video-player
      :options="playerOptions"
    />
</template>

