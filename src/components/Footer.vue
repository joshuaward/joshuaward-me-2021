<template lang="pug">
footer.footer
	.footer__inner
		.footer__section Made with&nbsp;&nbsp;
			i(class="fa-solid fa-heart")
			| &nbsp;&nbsp;by me.
		.footer__section © {{ getYear }}
</template>

<script>
export default {
	name: 'Footer',
  data() {
		return {
			
		}
	},
	methods: {},
	computed: {
		getYear: () => new Date().getFullYear()
	}
}
</script>

<style scoped lang="scss">
.footer {
	position: fixed;
  bottom: 0;
	left: 0;
	right: 0;
	padding-top: 2rem;
	padding-bottom: 2rem;
	background-color: darken($primary, 30%);
	color: $white;
	z-index: -2;
	&__inner {
		@include container;
		display: flex;
    justify-content: space-between;
	}
	&__section {
		display: flex;
		align-items: center;
		color: $white;
		font-size: 0.875rem;
		i {
			color: $accent;
			font-size: 0.75rem;
		}
	}
}
</style>