<template>
	<div class="search">
    Search Youtube
		<input type="text" name="name" v-model="searchText" @keypress="search">    
	</div>
</template>

<script>
  import axios from 'axios'
	export default {
    data () {
			return {
        rootUrl: 'https://www.googleapis.com/youtube/v3/search',
				searchText: '',
        key: 'AIzaSyBKJ9vgj0TqHMJ-WqJclYrOzWjXJ6t60Cg'
			}
		},
    computed: {
      params () {
        return {
          part: 'snippet',
          key: this.key,
          q: this.searchText,
          type: 'video'
        }
      }
    },
    methods: {
      search () {
        if (!this.key) {
          throw new Error('API key is missing')
        }
        axios.get(this.rootUrl, {params: this.params})
          .then(response => {
            // console.debug(response.data.items)
            this.$emit('getResults', response.data.items)
          })
      }
    }
	}
</script>

<style>
	.search {
		font-weight: bold;
	}
</style>