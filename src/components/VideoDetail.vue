<template>
  <div
    class="float-right col-xs-12 col-sm-12 col-md-7 col-lg-8 col-xl-8 "
    v-if="video"
  >
    <div class="embed-responsive embed-responsive-16by9 mt-3 ml-5">
      <iframe
        width="860"
        height="484"
        :src="selectedVideoURL"
        frameborder="0"
        allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture"
        allowfullscreen
      ></iframe>
    </div>
    <div class="details mt-2 p-2 ml-5">
      <h4>{{ video.snippet.title }}</h4>
      <p>{{ video.snippet.description }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'VideoDetail',
  props: ['video'],
  computed: {
    selectedVideoURL: function() {
      console.log(this.video.id.videoId);
      return `https://www.youtube.com/embed/${this.video.id.videoId}`;
    }
  }
};
</script>

<style scoped>
.details {
  border: 1x solid #ddd;
  border-radius: 4px;
}
</style>
