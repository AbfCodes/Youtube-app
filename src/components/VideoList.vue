<template>
  <div>
    <video-list-item
      v-for="video in allVideos"
      :video="video"
      :key="video.etag"
      @videoSelect="onVideoSelect"
    ></video-list-item>
  </div>
</template>

<script>
import VideoListItem from './VideoListItem';

export default {
  props: {
    allVideos: Array
  },
  name: 'VideoList',
  components: {
    videoListItem: VideoListItem
  },
  methods: {
    onVideoSelect(video) {
      this.$emit('videoSelect', video);
    }
  }
};
</script>

<style></style>
