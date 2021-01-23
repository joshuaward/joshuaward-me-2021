<template lang="pug">
header.header(:class="{'is-active': menuOpen}")
	.header__inner
		router-link.header__logo(to="/")
			//- svg(version="1.1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px" viewbox="0 0 50 50" style="enable-background:new 0 0 50 50;" xml:space="preserve")
			//- 	circle.header__logo-circle(cx="25" cy="25" r="25")
			//- 	polygon.header__logo-mountains(points="34.1,25 27.7,13.9 21.3,25 19.2,28.7 16.5,24 13,30 9.5,36.1 14.9,36.1 16.5,36.1 23.5,36.1 27.7,36.1 40.5,36.1")
		button.header__hamburger(@click="menuOpen = !menuOpen")
			span
		nav.header__nav
			ul.header__nav-list
				li.header__nav-list-item(v-for="item in navItems")
					a.header__nav-list-link(href="item.href") {{ item.label }}
</template>

<script>
export default {
  name: 'Header',
  data() {
		return {
			menuOpen: false,
			navItems: [
				{ "href": "#work",
					"label": "Work" },
				{ "href": "#skills",
					"label": "Skills" },
				{ "href": "#about",
					"label": "About" },
				{ "href": "/Resume",
					"label": "Resume" },
				{ "href": "mailto:joshua.ward@me.com",
					"label": "Hire Me!" }
			]
		}
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
	background-color: rgba($primary,0.125);
	z-index: 9999;
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
		width: 1.875rem;
		height: 1.875rem;
		background-color: $accent;
		border-radius: 50%;
		// svg {
		// 	position: relative;
		// 	width: 100%;
		// 	height: 100%;
		// }
		// &-circle {
		// 	fill: $accent;
		// 	transition: fill 0.25s linear;
		// }
		// &-mountains {
		// 	fill: $white;
		// 	transition: fill 0.25s linear;
		// }
	}
	&__hamburger {
		position: relative;
		display: block;
		width: 2.5rem;
		height: 2.5rem;
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
			&::before, 
			&::after {
				content: '';
				position: absolute;
				left: 0;
				width: 1.5rem;
				height: 0.125rem;
				background-color: $primary;
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
					background-color: $accent;
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
		position: fixed;
		top: 0;
		right: -90vw;
		width: 90vw;
		height: 100vh;
		margin: 0;
		padding: 3rem 0;
		background-color: transparentize($primary,0.05);
		transition: right 150ms linear;
		z-index: 998;
		@include mq(md) {
			width: var(--sm);
		}
		.is-active & {
			right: 0;
			transition: right 150ms linear;
			&::before {
				position: fixed;
				content: '';
				top: 0;
				right: 0;
				width: 100%;
				height: 100%;
				background-color: rgba($black,0.4);
				transition: right 150ms linear;
				z-index: 0;
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
								transition-delay: #{$i * 0.1}s;
							}
						}
					}
			}
			&-link {
				display: block;
				font-family: $fontFamilyHeadings;
				font-size: 1.25rem;
				font-weight: 400;
				color: $white;
				text-decoration: none;
				transform: translateX(100%);
				transition: 0.25s ease;
				.is-active & {
					transform: translateX(0);
					
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
		}

		.social {
			position: absolute;
			bottom: 1.25rem;
			display: flex;
			align-items: center;
			justify-content: space-between;
			width: 100%;
			padding: 0 1.25rem 0 2.5rem;

			> h5 {
				position: relative;
				display: block;
				width: 100%;
				color: $white;
			}

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
</style>
