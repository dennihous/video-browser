<template>
  <div>
    <SearchBar v-on:termChange="onTermChange" ></SearchBar>
  </div>
</template>

<script>
  import SearchBar from './components/SearchBar'
  const API_KEY = 'AIzaSyBL3tstLEU1hNWoHXTXMQ4TXBKf-L1axMA';

  export default {
    name: 'App',
    components: {
      SearchBar
    },
    methods: {
      onTermChange: function(searchTerm){
        console.log(searchTerm)
      }
    }
  }
</script>