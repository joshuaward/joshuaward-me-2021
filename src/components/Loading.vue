<template lang="pug">
section.loading
	.loader
		- for(i = 0; i < 9; i++) {
			div
		- }
</template>

<script>
export default {
	name: 'Loading',
  data() {
		return {}
	},
	methods: {},
	mounted() {}
}
</script>

<style scoped lang="scss">
.loading {
	position: fixed;
	top: 0;
	left: 0;
	right: 0;
	bottom: 0;
	display: flex;
	align-items: center;
	justify-content: center;
	width: 100%;
	height: 100%;
	background-color: rgba($whitesmoke, 0.75);
	opacity: 0;
	pointer-events: none;
	transition: opacity $base-duration ease;
	visibility: hidden;
	z-index: 99999999;
	.no-scroll & {
		opacity: 1;
		transition: opacity $base-duration ease;
		visibility: visible;
	}
}

.loader {
	position: relative;
	display: grid;
	grid-template-columns: 33% 33% 33%;
	grid-gap: 0.125rem;
	width: 6.25rem;
	height: 6.25rem;
	> div {
		position: relative;
		width: 100%;
		height: 100%;
		background: $accent;
		transform: scale(0.0);
		transform-origin: center center;
		animation: loader 1.5s infinite linear;		
		&:nth-of-type(1),
		&:nth-of-type(5), 
		&:nth-of-type(9) {
			animation-delay: 0.4s;
		}
		&:nth-of-type(4),
		&:nth-of-type(8) {
			animation-delay: 0.2s;
		}
		&:nth-of-type(2),
		&:nth-of-type(6) {
			animation-delay: 0.6s;
		}
		&:nth-of-type(3) {
			animation-delay: 0.8s;
		}
	}
}

@keyframes loader {
	0%   { transform: scale(0.0); }
	40%  { transform: scale(1.0); }
	80%  { transform: scale(1.0); }
	100% { transform: scale(0.0); }
}
</style>