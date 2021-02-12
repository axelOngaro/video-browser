<template>
  <ul>
    <VideoListItem v-for="video in videos" :key="video.etag" :video="video" />
  </ul>
</template>

<script>
import VideoListItem from "./VideoListItem";
export default {
  name: "VideoList",
  components: {
    VideoListItem,
  },
  props: {
    videos: Array,
  },
};
</script>

<style scoped>
ul {
  list-style: none;
  font-family: Arial, Helvetica, sans-serif;
  display: flex;
  flex-direction: column;
  justify-content: space-around;
}
</style>
