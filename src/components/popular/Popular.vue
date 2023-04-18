<template>
	<div class="popular-container">
		<div
			class="popular-card-container"
			v-for="item in cardContents"
			:key="item.ranking"
		>
			<PopularCard
				:image="item.image"
				:ranking="item.ranking"
				:header="item.header"
				:snippet="item.snippet"
			/>
		</div>
	</div>
</template>

<script setup>
	import { ref } from "vue";
	import PopularCard from "./PopularCard.vue";
	import retroImage from "@/assets/images/retro-pcs.jpg";
	import laptopImage from "@/assets/images/image-top-laptops.jpg";
	import gamingImage from "@/assets/images/gaming-growth.jpg";

	const cardContents = ref([
		{
			image: retroImage,
			ranking: "01",
			header: "Reviewing Retro PCs",
			snippet: "What happens when old PCs are given modern upgrades?",
		},
		{
			image: laptopImage,
			ranking: "02",
			header: "Top 10 Laptops of 2022",
			snippet: "Our best picks for various needs and budgets.",
		},
		{
			image: gamingImage,
			ranking: "03",
			header: "The Growth of Gaming",
			snippet: "How the pandemic has sparked fresh opportunities",
		},
	]);
</script>

<style lang="scss" scoped>
	.popular-container {
		margin: 4rem auto;
		display: grid;
		grid-template-columns: 1fr;
		gap: 1rem;

		.popular-card-container {
			padding-right: 1rem;
		}
	}

	@media (min-width: 769px) {
		.popular-container {
			display: grid;
			grid-template-columns: 1fr 1fr 1fr;
			width: 100%;
			margin: 0;
			gap: 1rem;

			.popular-card-container {
				padding: 0;
			}
		}
	}
</style>
