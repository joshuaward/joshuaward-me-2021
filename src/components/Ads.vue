<template lang="pug">
section.ads
	.ads__inner
		a.ads__link(href="https://www.tkqlhce.com/click-100963303-15015463" target="_blank")
			img.ads__image(src="https://www.tqlkg.com/image-100963303-15015463" alt="" border="0")
		a.ads__link.ads__link--no-image(href="https://www.kqzyfj.com/click-100973154-13756265" target="_blank")
			| NordVPN 1 year deal with 58% off for $5.00/mo
			img.ads__image(src="https://www.awltovhc.com/image-100973154-13756265" border="0")
</template>
	
	<script>
	export default {
		name: 'Ads',
		data() {
			return {
				
			}
		},
		methods: {},
		mounted() {}
	}
	</script>
	
	<style scoped lang="scss">
	.ads {
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
			display: flex;
			flex-direction: column;
			gap: 1rem;
			@include mq(md) {
				flex-direction: row;
				align-items: stretch;
				justify-content: center;
			}
		}
		&__link {
			position: relative;
			display: flex;
			@include mq(md) {
				flex: 0 1 25%;
				
			}
			&::before {
				content: '';
				display: block;
				padding-bottom: 75%;
			}
			&--no-image {
				padding: 20px 10px;
				background: $accent;
				// border-radius: 0.625rem;
				color: $white;
				text-align: center;
				justify-content: center;
				@include mq(md) {
					align-items: center;
				}
				&::before {
					padding-bottom: 0;
				}

				.ads__image {
					display: none;
				}
			}
		}
		&__image {
			position: absolute;
			top: 0;
			right: 0;
			bottom: 0;
			left: 0;
			width: 100%;
			height: 100%;
			object-fit: cover;
		}
	}
	</style>