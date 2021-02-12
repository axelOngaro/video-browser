<template>
  <div class="app">
    <SearchBar @termChange="onTermChange" />
    <VideoDetail :video="selectedVideo" />
    <VideoList :videos="videos" @videoSelect="onVideoSelect" />
  </div>
</template>

<script>
import axios from "axios";
import SearchBar from "./components/SearchBar";
import VideoList from "./components/VideoList";
import VideoDetail from "./components/VideoDetail";
const API_KEY = "AIzaSyAyxijaTTkp_6vYVpAOewqIIC-mD0tFH1Q";

export default {
  name: "App",
  components: {
    SearchBar,
    VideoList,
    VideoDetail,
  },
  data() {
    return {
      videos: [],
      selectedVideo: null,
    };
  },
  methods: {
    onVideoSelect(video) {
      this.selectedVideo = video;
    },
    onTermChange(searchTerm) {
      axios
        .get("https://www.googleapis.com/youtube/v3/search", {
          params: {
            key: API_KEY,
            type: "video",
            part: "snippet",
            q: searchTerm,
          },
        })
        .then((res) => {
          this.videos = res.data.items;
        });
    },
  },
};
</script>

<style scoped>
.app {
  display: flex;
  align-items: center;
  flex-direction: column;
  width: 100vw;
  justify-content: start;
  height: 100vh;
}
</style>
