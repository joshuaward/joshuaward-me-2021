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
					"title": "React Tic Tac Toe",
					"description": "Simple tic tac toe built with React and deployed with Heroku. It keeps a log of moves and has the ability to move back to certain steps in the game without mutating the data.",
					"tools": ['React', 'CSS3', 'ES6'],
					"href": "https://tic-tac-toe--react.herokuapp.com/",
					"cta": "View Project"
				},
				{
					"title": "Parallax Mountains",
					"description": "Layered SVG mountains with offset parallax effect using jQuery.",
					"tools": ['HTML5', 'Sass', 'CSS3', 'jQuery'],
					"href": "https://tic-tac-toe--react.herokuapp.com/",
					"cta": "View Project"
				},
			]
		}
	}
}
</script>

<style scoped lang="scss">
.work {

	&__inner {
		@include container;
		position: relative;
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;

		@include mq(lg) {
			flex-direction: row;
			flex-wrap: wrap;
			flex: 1;
			align-items: flex-start;
			justify-content: space-between;
		}
	}
}
</style>