<template lang="pug">
article.work__item
	.work__item-inner
		h2.work__item-title {{ item.title }}
		p.work__item-description {{ item.description }}
		.work__item-tools {{ item.tools }}
		a.btn.btn--primary(:href="item.href") {{ item.cta }}

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
	display: flex;
	flex-direction: column;
	width: 100%;
	margin-bottom: 3.125rem;
	@include mq(md) {
		width: 100%;
	}

	@include mq(lg) {
		width: 45%;
	}
}
</style>