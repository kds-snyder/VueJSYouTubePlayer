<template>
	<ul>
       <li v-for="result in results">
       <img :src="result.snippet.thumbnails.default.url" alt="" />
          {{result.snippet.title}}
       </li>
    </ul>
</template>

<script>
	export default {
		props:
			['results']
	}
</script>

<style>

</style>