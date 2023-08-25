<template lang="pug">
header.header(:class="{'is-sticky': isSticky, 'is-active': menuOpen}")
	.header__inner
		a.header__logo(href="#top")
			img(src="@/assets/images/mountains.svg")
		button.header__hamburger(@click="menuOpen = !menuOpen")
			span
		nav.header__nav
			ul.header__nav-list
				li.header__nav-list-item(v-for="item in navItems")
					a.header__nav-list-link(@click="menuOpen = !menuOpen" :href="item.href") {{ item.label }}
				li.header__nav-list-item
					button.header__nav-list-link(@click="toggleNight" type="button") Night Mode
			.header__nav-social
				h5.header__nav-social-title Be Social
				ul.header__nav-social-list
					li.header__nav-social-item(v-for="item in socialItems")
						a.header__nav-social-link(:href="item.href" target="_blank")
							span.sr-only {{ item.label }}
							i(:class="item.icon")

</template>

<script>
export default {
  name: 'Header',
  data() {
		return {
			menuOpen: false,
			isSticky: false,
			navItems: [
				{ 
					"href": "#work",
					"label": "Work" 
				},
				{ 
					"href": "#skills",
					"label": "Skills" 
				},
				{ 
					"href": "#about",
					"label": "About" 
				},
				// { 
				// 	"href": "/Resume",
				// 	"label": "Resume" 
				// },
				{ 
					"href": "mailto:joshua.ward@me.com",
					"label": "Hire Me!" 
				}
			],
			socialItems: [
				{ 
					"href": "https://codepen.io/joshuaward/pens/popular/",
					"label": "CodePen",
					"icon": "fab fa-codepen"
				},
				{ 
					"href": "https://github.com/joshuaward",
					"label": "GitHub" ,
					"icon": "fab fa-github"
				},
				{ 
					"href": "https://dribbble.com/joshuaward",
					"label": "Dribbble" ,
					"icon": "fab fa-dribbble"
				},
				{ 
					"href": "https://www.linkedin.com/in/joshuawward/",
					"label": "LinkedIn" ,
					"icon": "fab fa-linkedin"
				}
			],
		}
	},
	methods: {
		stickyHeader() {
			const header = document.querySelector('.header');
			const sticky = header.offsetTop;
			if(window.scrollY > sticky) {
				this.isSticky = true;
			} else {
				this.isSticky = false;
			}
		},
		toggleNight() {
			document.body.classList.toggle('night');
			this.menuOpen = false;
		}
	},
	mounted() {
		window.addEventListener('scroll', this.stickyHeader);
	},
	destroy() {
		window.removeEventListener('scroll', this.stickyHeader)
	}
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.header {
	position: fixed;
	top: 0;
	left: 0;
	right: 0;
	padding-top: 0.75rem;
	padding-bottom: 0.75rem;
	z-index: 9999;
	&.is-sticky {
		background-color: rgba($white,0.6);
		box-shadow: 0 0 0.3125rem rgba($black,0.2);
		transition: 0.25s linear;
		.night & {
			background-color: transparentize($night,0.1);
			box-shadow: 0 0 0.3125rem rgba(0,0,0,0.2);
			transition: 0.15s linear;
		}
	}
	&__inner {
		// @include container;
		display: flex;
		align-items: center;
		justify-content: space-between;
		margin-left: 2rem;
		margin-right: 2rem;
	}
	&__logo {
		display: flex;
		align-items: center;
		justify-content: center;
		width: 2.5rem;
		height: 2.5rem;
		.is-sticky & {
			width: 1.875rem;
			height: 1.875rem;
		}
		img {
			width: 100%;
			height: 100%;
		}
	}
	&__hamburger {
		position: relative;
		display: block;
		flex: 0 1 1.75rem;
		width: 1.5em;
		height: 1.875rem;
		padding: 0;
		background-color: transparent;
		border: 0;
		cursor: pointer;
		z-index: 999;
		> span {
			position: absolute;
			top: 50%;
			left: 50%;
			width: 1.5rem;
			height: 0.125rem;
			background-color: $primary;
			transform: translate(-50%,-50%);
			.night & {
				background-color: $accent;
			}
			&::before, 
			&::after {
				content: '';
				position: absolute;
				left: 0;
				width: 1.5rem;
				height: 0.125rem;
				background-color: $primary;
				.night & {
					background-color: $accent;
				}
			}

			&::before {
				transform: translateY(-0.3125rem);
				animation: burger1 250ms linear;
			}

			@keyframes burger1 {
				0%   { transform: translateY(0); }
				50%  { transform: translateY(0); }
				100% { transform: translateY(-0.3125rem) rotate(0deg); }
			}

			&::after {
				transform: translateY(0.3125rem);
				animation: burger2 250ms linear;
			}

			@keyframes burger2 {
				0%   { transform: translateY(0); }
				50%  { transform: translateY(0); }
				100% { transform: translateY(0.3125rem) rotate(0deg); }
			}
		}
		.is-active & {
			> span {
				visibility: hidden;

				&::before, 
				&::after {
					visibility: visible;
					background-color: $white;
					transform-origin: center center;
					transform: translateY(0);
					transition: all 250ms linear;
				}

				&::before {
					transform: rotate(-45deg);
					animation: burger3 250ms linear;
				}

				@keyframes burger3 {
					0%   { transform: translateY(0); }
					50%  { transform: translateY(0); }
					100% { transform: translateY(0) rotate(-45deg); }
				}

				&::after {
					transform: rotate(45deg);
					animation: burger4 250ms linear;
				}

				@keyframes burger4 {
					0%   { transform: translateY(0); }
					50%  { transform: translateY(0); }
					100% { transform: translateY(0) rotate(45deg); }
				}
			}
		}
	}
	&__nav {
		position: absolute;
		top: 0;
		left: 0;
		width: 100vw;
		height: 100vh;
		margin: 0;
		padding: 3rem 0;
		pointer-events: none;
		opacity: 0;
		visibility: hidden;
		transition: opacity 0.25s linear;
		z-index: 998;
		&::before,
		&::after {
			content: '';
			position: absolute;
			top: 0;
			bottom: 0;
			width: 50vw;
			height: 100vh;
			background-color: rgba($primary,0.9);
			backdrop-filter: blur(0);
			transition: all 0.25s ease;
			z-index: -1;;
		}
		&::before {
			left: -50vw;
			@include mq(md) {
				left: -60vw;
				width: 60vw;
				background-color: rgba($black,0.5);
			}
			@include mq(lg) {
				left: -70vw;
				width: 70vw;
				background-color: rgba($black,0.5);
			}
		}
		&::after {
			right: -50vw;
			@include mq(md) {
				right: -40vw;
				width: 40vw;
				background-color: rgba($primary,0.9);
			}
			@include mq(lg) {
				right: -30vw;
				width: 30vw;
				background-color: rgba($primary,0.9);
			}
		}
		.is-active & {
			pointer-events: all;
			opacity: 1;
			visibility: visible;
			&::before,
			&::after {
				backdrop-filter: blur(0.1875rem);
				transition: all 0.25s ease;
			}
			&::before {
				left: 0;
			}
			&::after {
				right: 0;
			}
		}
		&-list {
			position: relative;
			list-style-type: none;
			&-item {
				position: relative;
				margin: 5px 0;
				padding: 0.625rem 1.25rem;
				text-align: right;
				.night__mode {
					margin: 0;
					padding: 0;
					border: none;
					background-color: transparent;
					color: $white;
					font-size: 18px;
					&:hover {
						color: $accent;
					}
				}
				@for $i from 1 through 5 {
						&:nth-child(#{$i}) {
							.header__nav-list-link {
								transition-delay: #{$i * 0.09}s;
								.is-active & {
									transition-delay: 0;
								}
							}
						}
					}
			}
			&-link {
				display: inline-block;
				font-family: $fontFamilyHeadings;
				font-size: 1.25rem;
				font-weight: 400;
				color: $white;
				text-decoration: none;
				transform: translateX(200%);
				transition: 0.25s ease;
				.is-active & {
					transform: translateX(0);
					transition: 0.15s ease;
				}
				&::before {
					position: absolute;
					content: '';
					top: 50%;
					right: 0;
					width: 0%;
					height: 0.0625rem;
					z-index: 1;
					background-color: $accent;
					transition: width 500ms ease-in-out;
				}

				&:hover,
				&:focus {

					&::before {
						right: 0;
						width: 100%;
					}
				}

				&.hire-me {
					color: $accent;
				}
			}
			button.header__nav-list-link {
				background-color: transparent;
				border: 0;
				color: darken($primary,20%);
				font-weight: bold;
				text-shadow: 1px 1px 0 rgba($accent,0.6);
				cursor: pointer;
				.night & {
					color: $night;
					text-shadow: 1px 1px 0 $primary;
				}
			}
		}

	&-social {
			position: absolute;
			bottom: 1.25rem;
			display: flex;
			align-items: center;
			justify-content: flex-end;
			width: 100%;
			padding: 0 1.25rem 0 2.5rem;
			transform: translateX(100%);
			transition: 0.5s ease;
			.is-active & {
				transform: translateX(0);
				transition: 0.5s ease;
			}
			&-title {
				position: relative;
				display: block;
				color: $whitesmoke;
				font-family: $fontFamilyBase;
				font-size: 0.875rem;
				font-weight: bold;
				text-transform: uppercase;
			}
			&-list {
				display: flex;
				align-items: center;
				justify-content: flex-end;
				list-style: none;
			}
			&-item {
				> a {
					position: relative;
					display: inline-block;
					margin: 0 0.625rem;
					color: $white;
					&:hover {
						color: $accent;
					}
				}
			}

		}
	}
}
</style>
