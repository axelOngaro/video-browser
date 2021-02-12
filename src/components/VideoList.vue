<template>
  <ul>
    <VideoListItem
      v-for="video in videos"
      :key="video.etag"
      :video="video"
      @videoSelect="onVideoSelect"
    />
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
  methods: {
    onVideoSelect(video) {
      this.$emit("videoSelect", video);
    },
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
