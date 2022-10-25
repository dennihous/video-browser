<template>
  <div class="container">
    <SearchBar v-on:termChange="onTermChange" ></SearchBar>
    <VideoList v-bind:videos="videos"></VideoList>
  </div>
</template>

<script>
  import axios from 'axios'
  import SearchBar from './components/SearchBar'
  import VideoList from './components/VideoList'

  const API_KEY = 'AIzaSyBL3tstLEU1hNWoHXTXMQ4TXBKf-L1axMA';

  export default {
    name: 'App',
    components: {
      SearchBar,
      VideoList
    },
    data: function() {
      return { videos: [] }
    },
    methods: {
      onTermChange: function(searchTerm){
        axios.get('https://www.googleapis.com/youtube/v3/search', {
          params: {
            key: API_KEY,
            type: 'video',
            part: 'snippet',
            q: searchTerm
          }
        }).then(response => {
          this.videos = response.data.items
        })
      }
    }
  }
</script>