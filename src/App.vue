<template lang="pug">
#app
	Header
	Hero
	Work
</template>

<script>
import Header from './components/Header.vue'
import Hero from './components/Hero.vue'
import Work from './components/Work.vue'

export default {
	name: 'App',
	components: {
		Header,
		Hero,
		Work
	}
}
</script>

<style lang="scss">
*, *:before, *:after {
	box-sizing: border-box;
	outline: none;
}

html {
	font-family: $fontFamilyHeadings;
	font-size: 16px;
	font-smooth: auto;
	font-weight: 300;
	line-height: 1.5;
	color: #444;
}

body {
	margin: 0;
	padding: 0;
}
</style>
