<template>
  <li>
    <img :src="thumbnailUrl" alt="" />
    {{ video.snippet.title }}
  </li>
</template>

<script>
export default {
  name: "VideoListItem",
  props: {
    video: Object,
  },
  computed: {
    thumbnailUrl() {
      return this.video.snippet.thumbnails.default.url;
    },
  },
};
</script>
<style scoped>
li {
  border: 1px solid rgb(199, 199, 199);
  height: 100%;
  display: flex;
  justify-content: flex-start;
  align-items: center;
  cursor: pointer;
  border-radius: 10px;
}
li:hover {
  transform: translate3d(10px, 0px, 0px);
  background-color: #eee;
}
img {
  margin-right: 25px;
}
</style>
