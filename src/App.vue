<template lang="pug">
#pageWrap
	Loading(v-if="loading")
	Header
	Hero
	Ads
	Work
	Skills
	About
</template>

<script>
import Header from './components/Header.vue'
import Hero from './components/Hero.vue'
import Ads from './components/Ads.vue'
import Work from './components/Work.vue'
import Skills from './components/Skills.vue'
import About from './components/About.vue'
import Footer from './components/Footer.vue'
import Loading from './components/Loading.vue'

export default {
	name: 'App',
	components: {
		Loading,
		Header,
		Hero,
		Ads,
		Work,
		Skills,
		About,
		Footer
	},
	data() {
		return {
			loading: false
		}
	},
	mounted() {
		this.loading = true
		document.body.classList.add('no-scroll');
		const randomNumber = Math.floor(Math.random() * 5);

		console.log(randomNumber);

		setTimeout(() => {
			this.loading = false
			document.body.classList.remove('no-scroll');
		}, (randomNumber * 1000));
	}
}
</script>

<style lang="scss">
*, *:before, *:after {
	box-sizing: border-box;
	outline: none;
}

html {
	font-family: $fontFamilyBase;
	font-size: 16px;
	font-smooth: auto;
	font-weight: 300;
	line-height: 1.5;
	color: $text;
	scroll-behavior: smooth;
}

body {
	margin: 0;
	padding: 0;
	&.no-scroll {
		overflow: hidden !important;
	}
	&.night {
		.modal {
			article {
				p, h3 {
					color: $primary;
				}
			}
		}
	}
}

h1,
h2,
h3,
h4,
h5,
h6,
hgroup,
hr,
ul,
ol,
dl,
blockquote,
p,
address,
figure,
pre {
	margin: 0 0 $marginBase;
}

h1,
h2,
h3,
h4,
h5,
h6,
.h1,
.h2,
.h3,
.h4,
.h5,
.h6 {
	font-family: $fontFamilyHeadings;
	font-weight: $fontWeightHeadings;
	line-height: $lineHeightHeadings;
	.night & {
		color: $white;
		transition: 0.15s linear;
	}
}

h1,
.h1 {
	font-size: $h1Size;
}

h2,
.h2 {
	font-size: $h2Size;
}

h3,
.h3 {
	font-size: $h3Size;
}

h4,
.h4 {
	font-size: $h4Size;
}

h5,
.h5 {
	font-size: $h5Size;
}

h6,
.h6 {
	font-size: $h6Size;
}

hr {
	margin-top: $marginBase;
	border: none;
	border-top: 1px solid;
}

a {
	transition: all 0.25s ease-in-out;
	color: $linkColorBase;
	text-decoration: none;
	background-color: transparent; 
	-webkit-text-decoration-skip: objects; 
	&:hover {
		color: $linkColorHoverBase;
		text-decoration: underline;
	}
}
p {
	.night & {
		color: $white;
		transition: 0.15s linear;
	}
}

a {
	text-decoration: none;
}

.btn {
	position: relative;
	display: flex;
	align-items: center;
	justify-content: center;
	width: 8.125rem;
	margin: 1.25rem 0;
	padding: 0.5rem 1.5rem;
	background-color: $accent;
	border: 2px solid $accent;
	border-radius: 6.1875rem;
	box-shadow: 
		0 0.875rem 1.75rem rgba(0,0,0,0.15), 
		0 0.625rem 0.625rem rgba(0,0,0,0.12);
	transition: all 0.25s cubic-bezier(.25,.8,.25,1);
	color: $white;
	font-size: 0.875rem;
	transition: 0.25s linear;
	&:hover {
		background-color: $white;
		box-shadow: 
			0 0.0625rem 0.1875rem rgba(0,0,0,0.06), 
			0 0.0625rem 0.125rem rgba(0,0,0,0.12);
		color: $accent;
		text-decoration: none;
	}
	&--large {
		width: 15.625rem;
		height: 2.5rem;
		margin: 1.25rem 0;
		padding: 1.25rem 2.5rem;
	}
	&--muted {
		background-color: $white;
		color: $primary;
		box-shadow: 
			0 0.0625rem 0.1875rem rgba(0,0,0,0.06), 
			0 0.0625rem 0.125rem rgba(0,0,0,0.12);
		transition: all 0.25s cubic-bezier(.25,.8,.25,1);
		&:hover {
			background-color: $accent;
			color: $white;
			box-shadow: 
				0 0.875rem 1.75rem rgba(0,0,0,0.15), 
				0 0.625rem 0.625rem rgba(0,0,0,0.12);
		}
	}
}
</style>
