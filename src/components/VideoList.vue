<template>
  <div :class="listGriding">
    <ul>
      <strong v-if="ifVideo" class="pl-2">Up Next</strong>
      <video-list-item
        v-for="video in allVideos"
        :video="video"
        :key="video.etag"
        @videoSelect="onVideoSelect"
      ></video-list-item>
    </ul>
  </div>
</template>

<script>
import VideoListItem from './VideoListItem';

export default {
  props: ['allVideos', 'ifVideo'],
  name: 'VideoList',
  components: {
    videoListItem: VideoListItem
  },
  computed: {
    listGriding() {
      if (this.ifVideo) {
        return {
          'col-xs-12': true,
          'col-sm-12': true,
          'col-md-5': true,
          'col-lg-4': true,
          'col-xl-4': true
        };
      } else {
        return {
          'col-xs-12': true,
          'col-sm-12': true,
          'col-md-8': true,
          'col-lg-8': true,
          'col-xl-8': true
        };
      }
    },

    centerAllList() {
      if (this.ifVideo) {
        return {
          'text-center': true
        };
      } else return { 'text-center': false };
    }
  },
  methods: {
    onVideoSelect(video) {
      this.$emit('videoSelect', video);
    }
  }
};
</script>

<style scoped>
ul {
  float: right !important;
}
</style>
