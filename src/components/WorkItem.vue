<template lang="pug">
article.work__item
	.work__item-inner
		h2.work__item-title {{ item.title }}
		p.work__item-description {{ item.description }}
		.work__item-tools
			div Tools
			span(v-for="tool in item.tools")  {{ tool }}
		a.btn(:href="item.href" :target="item.target") {{ item.cta }}

</template>

<script>
export default {
	name: 'WorkItem',
	props: ['item'],
  data() {
		return {
			
		}
	}
}
</script>

<style scoped lang="scss">
.work__item {
	position: relative;
	padding: 1.25rem;
	margin-bottom: 3.125rem;
	border-radius: 0.625rem;
	@include mq(md) {
		max-width: 100%;
		margin-bottom: 2rem;
		padding: 1.75rem;
	}
	&-inner {
		display: flex;
		flex-direction: column;
		width: 100%;
		height: 100%;
	}
	&-title {
		margin-top: 0;
		font-family: $fontFamilyHeadings;
		font-weight: bold;
	}
	&-description {
		// flex: 1 0 auto;
		margin-top: 0;
	}
	&-tools {
		position: relative;
		display: block;
		margin-bottom: 1rem;

		> div {
			position: relative;
			margin: 0 0 0.5rem;
			color: lighten($text,10%);
			font-size: 0.6875rem;
			text-transform: uppercase;
		}

		span {
			position: relative;
			display: inline-block;
			margin: 0 0.5rem 0.5rem 0;
			padding: 0.3125rem 1rem;
			background-color: $primary;
			border-radius: 6.1875rem;
			color: $white;
			font-size: 0.75rem;
			font-weight: 300;
		}
	}
}
</style>