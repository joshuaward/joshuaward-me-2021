<template lang="pug">
section#about.about.watch
	.about__inner
		.about__image
			img(src="../assets/images/me.png" alt="Joshua Ward")
		.about__bio
			p.about__bio-copy Hi. My name is Joshua Ward. I design and build websites. Originally from South Dakota, I moved to the Denver area about {{ yearsLived }} years ago. My mission in life is to be a respectable human being and make a positive impact on the people I encounter. In my free time, I enjoy traveling, skateboarding, snowboarding, art, the Rocky Mountains, hiking, and music. I graduated Cum Laude from Arizona State University with a Bachelor's degree in Web Design & Internet Development in 2011. I also have an Associate's degree in Graphic Design for print from Scottsdale Community College.
</template>

<script>
export default {
	name: 'About',
  data() {
		return {
			
		}
	},
	computed: {
		yearsLived() {
			return new Date().getFullYear() - 2015;
		}
	},
	methods: {
		observeBio() {
			const options = { threshold: [0] };
			const handleIntersect = (entries) => {
				entries.forEach(entry => {
					entry.target.setAttribute('on-screen', entry.isIntersecting);
					if(entry.isIntersecting) {
						document.body.querySelector('.about__image img').classList.add('is-intersecting')
					} else {
						document.body.querySelector('.about__image img').classList.remove('is-intersecting')
					}
				})
			}
			const observer = new IntersectionObserver(handleIntersect, options);
			const watchers = document.querySelectorAll('.watch');
			watchers.forEach(w => observer.observe(w));
		},
		bioImage() {
			// const about = document.querySelector('.about');
			// const bioImage = document.querySelector('.about__image img');
			// console.log('offsetTop', about.offsetTop)

			// if(bioImage.classList.contains('is-intersecting')) {
			// 	let index = about.offsetTop - window.pageYOffset;
			// 	console.log(index * 0.2);
			// 	bioImage.style.transform = `translateY(${index * 0.05}%)`
			// } else {
			// 	console.log(false)
			// }
		}
	},
	mounted() {
		this.observeBio();
		window.addEventListener('scroll', this.bioImage);
	}
}
</script>

<style scoped lang="scss">
.about {
	position: relative;
	width: 100%;
	padding: 4.6875rem 0;
	
	box-shadow: 0 0 1.25rem rgba($black,0.4);
	font-family: $fontFamilyHeadings;
	line-height: 1.75;
	z-index: 0;
	&::before,
	&::after {
		content: '';
		position: absolute;
		top: 0;
		left: 0;
		right: 0;
		bottom: 0;
		width: 100%;
		height: 100%;
		// opacity: 0.1;
		
	}
	&::before {
		background-color: darken($primary, 30%);
		opacity: 0.987;
		z-index: -1;
	}
	&::after {
		background-image: url('https://www.toptal.com/designers/subtlepatterns/patterns/positive.png');
		z-index: -2;
	}


		&__inner {
			@include container;
			display: flex;
			flex-direction: column;
			align-items: center;
			z-index: 2;
			@include mq(md) {
				flex-direction: row;
			}
		}
		&__image {
			position: relative;
			display: flex;
			align-items: center;
			justify-content: center;
			width: 12.5rem;
			height: 12.5rem;
			margin-bottom: 2rem;
			@include mq(md) {
				flex: 0 1 30%;
			}
			@include mq(lg) {
				flex: 0 0 18.75rem;
				order: 2;
				width: 18.75rem;
				height: 18.75rem;
				// transform: translateY(-50%);
			}
			&::after {
				content: '';
				display: block;
				padding-bottom: 100%;
			}
			img {
				position: absolute;
				top: 0;
				left: 0;
				right: 0;
				bottom: 0;
				width: 100%;
				height: 100%;
				border-radius: 50%;
				box-shadow: 0 0 1.875rem rgba($black,0.3);
				object-fit: cover;
			}
		}
		&__bio {
			width: 100%;
			@include mq(md) {
				flex: 0 0 70%;
				padding: 1.5rem;
			}
			@include mq(lg) {
				flex: 0 1 auto;
				order: 1;
			}
			&-copy {
				position: relative;
				margin-bottom: 0;
				color: $white;
				&::before,
				&::after {
					position: absolute;
					left: 0;
					color: $accent;
					font-weight: bold;
				}
				&::before {
					content: '<about>';
					top: 0;
					transform: translateY(calc(-100% - 1rem));
				}
				&::after {
					content: '</about>';
					bottom: 0;
					transform: translateY(calc(100% + 1rem));
				}
			}
			&-image {
				position: relative;
				width: 50%;
				height: auto;
				margin: 0 auto 1.25rem;
				border-radius: 50%;
				@include mq(md) {
					width: 25%;
					margin: 1.25rem 1.25rem 0 0;
					float: left;
				}
				@include mq(lg) {
					width: 15%;
				}
			}
		}
	}
</style>