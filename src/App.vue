<template>
  <div id="app">
    
    <Search @getResults="updateResults"/>
    <List :results="results"/>
    <Player :videoId="selectedVideoId" />
  </div>
</template>

<script>
  import Search from './components/Search.vue'
  import List from './components/List.vue'
  import Player from './components/Player.vue'
  export default {
    name: 'app',
    components: {
      Search, List, Player
    },
    data () {
      return {
        results: [],
        selectedVideoId: ''
      }
    },
    methods: {
      updateResults (results) {
        this.results = results
      }
    }
  }
</script>

<style>
  
</style>