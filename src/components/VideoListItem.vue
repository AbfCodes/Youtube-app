<template>
  <li class="list-group-item media" @click="onVideoSelect">
    <img :src="thumbnailUrl" class="mr-3" alt="thumbnail icon" />
    <div class="media-body">
      <strong>{{ video.snippet.title }}</strong>
      <!-- <hr /> -->
      <span class="text-black mt-2 d-block">{{
        video.snippet.channelTitle
      }}</span>
    </div>
  </li>
</template>

<script>
export default {
  name: 'VideListItem',
  props: ['video'],
  methods: {
    onVideoSelect() {
      this.$emit('videoSelect', this.video);
    }
  },
  computed: {
    thumbnailUrl() {
      return this.video.snippet.thumbnails.default.url;
    }
  }
};
</script>

<style scoped>
li {
  display: flex;
  cursor: pointer;
  overflow: hidden;
  text-overflow: ellipsis;
}
li:hover {
  background-color: #eee;
}
</style>
