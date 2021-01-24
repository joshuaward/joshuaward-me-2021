<template lang="pug">
.skills__item
	button.skills__item-btn(@click="openModal" :data-modal-trigger="`trigger-${item.id}`") {{ item.title }}
	.modal(:class="{'is-open': modalOpen}" :data-modal="`trigger-${item.id}`")
		article.modal__content
			button.modal__close(@click="closeModal")
			.modal__header
				h3 {{ item.title }}
				.level.five-stars
			.modal__copy
				p {{ item.modal.description }}
				a.source(:href="item.modal.sourceHref" target="_blank") {{ item.modal.source }}

</template>

<script>
export default {
	name: 'SkillsItem',
	props: ['item'],
  data() {
		return {
			modalOpen: false
		}
	},
	methods: {
		openModal() {
			this.modalOpen = true
		},
		closeModal() {
			this.modalOpen = false
		}
	}
}
</script>

<style scoped lang="scss">
.skills__item {
	&-btn {
		position: relative;
		display: inline-block;
		align-items: center;
		justify-content: center;
		margin: 0 0.5rem 1.25rem 0;
		padding: 0.625rem 1.25rem;
		background-color: $accent;
		border: 0.0625rem solid $white;
		border-radius: 9.9375rem;
		transition: all 0.3s cubic-bezier(.25,.8,.25,1);
		color: $white;
		font-size: 0.75rem;
		font-weight: 300;
		text-transform: uppercase;
		cursor: pointer;
		&:hover {
			border: 0.0625rem solid $accent;
			box-shadow: 0 14px 28px rgba(0,0,0,0.25), 0 10px 10px rgba(0,0,0,0.22);
		}
	}
}

.modal {
	position: fixed;
	top: 0;
	left: 0;
	display: flex;
	align-items: center;
	justify-content: center;
	width: 100%;
	height: 100vh;
	background-color: rgba(0,0,0,0.8);
	opacity: 0;
	pointer-events: none;
	transition: opacity $base-duration;
	visibility: hidden;
	z-index: 9999;
	&.is-open {
		opacity: 1;
		pointer-events: all;
		visibility: visible;
		transition: opacity $base-duration;
	}
	&__close {
		position: absolute;
		top: 0.5rem;
		right: 0.5rem;
		display: flex;
		align-items: center;
		justify-content: center;
		width: 2.5rem;
		height: 2.5rem;
		border: none;
		background-color: transparent;
		font-size: 1.5rem;
		transition: $base-duration linear;
		cursor: pointer;
		&::before, 
		&::after {
			position: absolute;
			content: '';
			width: 1.25rem;
			height: 0.125rem;
			background-color: black;
		}
		&::before {
			transform: rotate(-45deg);
		}
		&::after {
			transform: rotate(45deg);
		}
		&:hover {
			transform: rotate(360deg);
			&::before, 
			&::after {
				background-color: $accent;
			}
		}
	}
	&__content {
		position: relative;
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: flex-start;
		width: 90%;
		margin: 0;
		padding: 1.875rem;
		background-color: white;
		border-radius: 0.3125rem;
		transform: scale(0.0);
		transition: transform $base-duration;
		z-index: 99999;
		@include mq(md) {
			width: 75%;
		}
		@include mq(lg) {
			width: 50%;
		}
		.is-open & {
			transform: scale(1.0);
			transition: transform $base-duration;
		}
	}
	&__header {
		position: relative;
		display: flex;
		flex-direction: column;
		// align-items: center;
		// justify-content: flex-start;
		width: 100%;
		margin: 0;
		padding: 0;
		h3 {
			margin-bottom: 0;
			font-size: 1.5rem;
			font-weight: bold;
		}
		.level {
			margin-bottom: 1.25rem;
			font-size: 1rem;
			> span {
				font-size: 0.75rem;
				text-transform: uppercase;
			}
		}
	}
	&__copy {
		position: relative;
		display: flex;
		flex-direction: column;
		width: 100%;
		p {
			margin-bottom: 1.25rem;
			font-size: 0.875rem;
			line-height: 1.75;
			.source {
				color: $accent;
			}
			.link {
				color: $accent;
				font-weight: 400;
			}
		}
	}
}

</style>