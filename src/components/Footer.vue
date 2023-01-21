<template lang="pug">
footer.footer
	.footer__inner

			h1 Footer
</template>

<script>
export default {
	name: 'Footer',
  data() {
		return {
			
		}
	},
	methods: {},
	mounted() {}
}
</script>

<style scoped lang="scss">
.footer {
	padding-top: 2rem;
	padding-bottom: 2rem;
	background-color: $white;
	@include mq(md) {
		padding-top: 3rem;
		padding-bottom: 3rem;
	}
	@include mq(lg) {
		padding-top: 4rem;
		padding-bottom: 4rem;
	}
	&__inner {
		@include container;
	}
}
</style>