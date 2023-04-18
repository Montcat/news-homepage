<template>
	<div class="popular-card">
		<div class="card-image .left">
			<img :src="image" alt="" />
		</div>

		<div class="card-content right">
			<span class="card-ranking"> {{ ranking }} </span>
			<a href="#" class="card-header">{{ header }}</a>
			<p class="card-snippet">
				{{ snippet }}
			</p>
		</div>
	</div>
</template>

<script setup>
	defineProps(["image", "ranking", "header", "snippet"]);
</script>

<style lang="scss" scoped>
	.popular-card {
		display: grid;
		grid-template-columns: 27svw 1fr;
		gap: 5svw;

		.card-image {
			height: 100%;

			img {
				object-fit: fill;
				width: 100%;
				height: 100%;
			}
		}

		.card-content {
			.card-ranking {
				font-size: 10svw;
				font-weight: 800;
				color: var(--neutral-grayish-blue);
			}

			.card-header {
				display: block;
				margin: 1rem auto;
				font-weight: 800;
				color: var(--neutral-very-dark-blue);
			}

			.card-header:hover {
				color: var(--primary-soft-red);
			}

			.card-snippet {
				color: var(--neutral-grayish-blue);
			}
		}
	}

	@media (min-width: 769px) {
		.popular-card {
			display: grid;
			grid-template-columns: 1fr 2fr;
			gap: 1rem;
			grid-template-rows: 9rem;

			.card-content {
				.card-ranking {
					font-size: 2rem;
				}
			}
		}
	}
</style>
