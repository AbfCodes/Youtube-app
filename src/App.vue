<template>
  <div class="container">
    <Searchbar @valCh="onvalCh"></Searchbar>
    <div class="row">
      <video-detail :video="selectedVideo"></video-detail>
      <video-list :allVideos="videos" @videoSelect="onVideoSelect"></video-list>
    </div>
  </div>
</template>
 
<script>
import axios from 'axios';

import Searchbar from './components/searchbar';
import VideoList from './components/VideoList';
import VideoDetail from './components/VideoDetail';

const API_KEY = 'AIzaSyB8KcX71Y5HdDDKsRqRHpCE8pfWmCQm4nY';

export default {
  name: 'App',

  data() {
    return { queryText: '', videos: [], selectedVideo: null };
  },
  components: { Searchbar, VideoList, VideoDetail },

  methods: {
    onvalCh(val) {
      this.queryText = val;
      axios
        .get('https://www.googleapis.com/youtube/v3/search', {
          params: {
            key: API_KEY,
            type: 'video',
            part: 'snippet',
            q: this.queryText,
            maxResults: 5
          }
        })
        .then(res => {
          this.videos = res.data.items;
        })
        .catch(err => console.error(err.message));
    },
    onVideoSelect(video) {
      this.selectedVideo = video;
      // console.log(this.selectedVideo.id.videoId);
    }
  }
};
</script>

<style></style>
