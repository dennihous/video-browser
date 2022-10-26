<template>
  <ul>
    <VideoListItem v-for="video in videos" 
    :key="video.etag" 
    v-bind:video="video"
    @videoSelect="onVideoSelect" 
    class="list-group">
      <!-- {{video}} -->
    </VideoListItem>
  </ul>
</template>

<script>
import VideoListItem from './VideoListItem'

  export default {
    name: 'VideoList',
    components: {
      VideoListItem
    },
    props: ['videos'],
    methods: {
      onVideoSelect(video) {
        this.$emit('videoSelect', video)
      }
    }
  }

</script>

<style>
</style>