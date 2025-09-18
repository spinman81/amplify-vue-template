<script setup>
import { ref } from "vue";
import { NButton, NInput, NInputGroup, NDivider, NFlex } from "naive-ui";
import { NConfigProvider, NGlobalStyle } from 'naive-ui';
import { darkTheme } from 'naive-ui';

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
  <n-config-provider :theme="darkTheme">
    <n-global-style />
    <div class="wrap">
      <n-input-group>
        <n-button type="primary">Play Stream</n-button>
        <n-input :placeholder="url" clearable></n-input>
        <n-button type="primary" ghost>Play</n-button>
      </n-input-group>
      <n-divider ></n-divider>
    </div>
    <n-flex justify="center">
      <video-player
        class="vjs-custom-skin"
        :options="playerOptions"
      />
    </n-flex>
    <n-divider ></n-divider>
  </n-config-provider>
</template>

<style scoped>
div.wrap {
  width: 98%;
  margin: auto;
  margin-top: 10px;
}
</style>

