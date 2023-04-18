<template>
	<div class="news-container">
		<h2 class="news-header">New</h2>

		<div class="news-content">
			<div class="news-item" v-for="item in articles" key="item.id">
				<Article
					:article-header="item.header"
					:article-content="item.content"
				/>
				<hr />
			</div>
		</div>
	</div>
</template>

<script setup>
	import { ref } from "vue";
	import Article from "./Article.vue";

	const articles = ref([
		{
			id: 1,
			header: "Hydrogen VS Electric Cars",
			content: "Will hydrogen-fueled cars ever catch up to EVs?",
		},
		{
			id: 2,
			header: "The Downsides of AI Artistry",
			content:
				"What are the possible adverse effects of on-demand AI image generation?",
		},
		{
			id: 3,
			header: "Is VC Funding Drying Up?",
			content:
				"Private funding by VC firms is down 50% YPY. We take a look at what that means.",
		},
	]);
</script>

<style lang="scss" scoped>
	.news-container {
		background-color: var(--neutral-very-dark-blue);
		padding: 1.5rem;
		margin: 4rem auto;

		.news-header {
			color: var(--primary-soft-orange);
			font-weight: 700;
			font-size: 2rem;
			margin-top: 0;
		}

		.news-content {
			.news-item > hr {
				margin: 2rem 0;
			}
		}
	}

	// Secting the removing the last hr elemnt
	.news-item:last-child > hr:nth-child(2) {
		display: none;
	}

	@media (min-width: 769px) {
		.news-container {
			margin: 0;
		}
	}
</style>
