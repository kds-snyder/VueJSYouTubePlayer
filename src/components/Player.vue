<template>
	<div>	
		<iframe 
		width="560" 
		height="315" 
		src="videoUrl"
		frameborder="0" 
		allowfullscreen>
		</iframe>
	</div>
</template>

<script>
	export default {
		props: ['videoId'],
		computed: {
			videoUrl () {
				return `https://www.youtube.com/embed/${this.videoId}`
			}
		}
	}
</script>

<style>
</style>