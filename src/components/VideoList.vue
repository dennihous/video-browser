<template>
  <ul>
    <VideoListItem v-for="video in videos" :key="video.etag" v-bind:video="video" class="list-group">
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
    props: ['videos']
  }
</script>

<style>
</style>