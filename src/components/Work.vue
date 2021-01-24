<template lang="pug">
section#work.work
	.work__inner
		WorkItem(v-for="(item,i) in workItems" :key="i" :item="item")
</template>

<script>
import WorkItem from '@/components/WorkItem.vue';

export default {
	name: 'Work',
	components: {
		WorkItem
	},
  data() {
		return {
			workItems: [
				{
					"title": "Vue Flag Guessing Game",
					"description": "An app that connects to the countries API and pulls in the country's name and flag. The game generates and array of multiple choice options, chooses a correct answer and then shuffles the array. Upon answering, a screen will appear that says whether you got it right or wrong. Then onto the next flag.",
					"tools": ['Vue', 'CSS3', 'ES6'],
					"href": "https://map-guessing-game.joshuaward.me/",
					"target": "_blank",
					"cta": "View Project"
				},
				{
					"title": "Vue Questionnaire",
					"description": "Vue app questionnaire carousel.",
					"tools": ['Vue', 'CSS3', 'ES6'],
					"href": "https://codepen.io/joshuaward/pen/LYEJGjQ",
					"target": "_blank",
					"cta": "View Project"
				},
				{
					"title": "Color Changing Hero Background",
					"description": "Simple tic tac toe built with React and deployed with Heroku. It keeps a log of moves and has the ability to move back to certain steps in the game without mutating the data.",
					"tools": ['JavaScript', 'CSS3', 'ES6'],
					"href": "https://codepen.io/joshuaward/pen/XWbyJVV",
					"target": "_blank",
					"cta": "View Project"
				},
				{
					"title": "Parallax Mountains",
					"description": "Layered SVG mountains with offset parallax effect using jQuery.",
					"tools": ['HTML5', 'Sass', 'CSS3', 'jQuery'],
					"href": "https://codepen.io/joshuaward/pen/vZoaNE",
					"target": "_blank",
					"cta": "View Project"
				},
				{
					"title": "Random Colored Pulsating Dots",
					"description": "Place random colored pulsating dots with a click using ES6 and Sass animations.",
					"tools": ['HTML5', 'Sass', 'CSS3', 'Babel', 'ES6', 'JavaScript'],
					"href": "https://codepen.io/joshuaward/pen/WZqyLQ",
					"target": "_blank",
					"cta": "View Project"
				},
				{
					"title": "JavaScript Form Validation",
					"description": "Form validation with user input to make sure you're not a robot. It also has floating labels!",
					"tools": ['HTML5', 'Sass', 'CSS3', 'Babel', 'ES6', 'JavaScript'],
					"href": "https://codepen.io/joshuaward/pen/OOJVmv",
					"target": "_blank",
					"cta": "View Project"
				},
				{
					"title": "Slide In on Scroll",
					"description": "Images that slide in on scroll.",
					"tools": ['HTML5', 'Sass', 'CSS3', 'Babel', 'ES6', 'JavaScript'],
					"href": "https://codepen.io/joshuaward/pen/GORKbX",
					"target": "_blank",
					"cta": "View Project"
				},
				{
					"title": "Fun with HTML5 Canvas",
					"description": "Draw with your mouse using ES6 and HTML5 canvas.",
					"tools": ['HTML5', 'Babel', 'ES6', 'JavaScript'],
					"href": "https://codepen.io/joshuaward/pen/QqRaoe",
					"target": "_blank",
					"cta": "View Project"
				},

				{
					"title": "Responsive Split Hidden Menu w/ Animation",
					"description": "Draw with your mouse using ES6 and HTML5 canvas.",
					"tools": ['HTML5', 'Babel', 'ES6', 'JavaScript'],
					"href": "https://codepen.io/joshuaward/pen/YvQdpr",
					"target": "_blank",
					"cta": "View Project"
				},
				{
					"title": "VueDo List",
					"description": "A simple browser to-do list that stores your tasks in local storage and removes them once deleted. It shows errors when you try to add a blank task. There are animations for completed tasks as well.",
					"tools": ['Vue', 'CSS3', 'SCSS', 'JavaScript'],
					"href": "https://tic-tac-toe--react.herokuapp.com/",
					"target": "_blank",
					"cta": "View Project"
				},
			]
		}
	}
}
</script>

<style scoped lang="scss">
.work {
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
	.night & {
		background-color: $night;
		transition: 0.15s linear;
	}
	&__inner {
		@include container;
		position: relative;
		display: grid;
		grid-template-columns: 1fr;
		grid-gap: 1rem;
		@include mq(md) {
			grid-template-columns: 1fr 1fr;
		}
	}
}
</style>