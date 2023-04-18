<template>
	<div class="hero-container">
		<div class="hero-image">
			<img
				src="@/assets/images/web-3-mobile.jpg"
				alt=""
				v-if="!isLargeScreen"
			/>
			<img src="/src/assets/images/web-3-desktop.jpg" alt="" v-else />
		</div>

		<div class="hero-content">
			<h2 class="hero-header">The Bright Future of Web 3.0?</h2>

			<div class="hero-snippet">
				<p class="hero-description">
					We dive into the next evolution of the web that claims to put the
					power of the platforms back into the hands of the people. But is it
					really fulfilling its promise?
				</p>

				<button class="hero-cta">READ MORE</button>
			</div>
		</div>
	</div>
</template>

<script setup>
	import { useMediaQuery } from "@vueuse/core";
	const isLargeScreen = useMediaQuery("(min-width: 769px)");
</script>

<style lang="scss" scoped>
	.hero-container {
		margin: 1rem 0;

		.hero-image {
			height: 35svh;
			width: 100%;

			img {
				object-fit: cover;
				width: 100%;
				height: 100%;
			}
		}

		// Hero content section
		.hero-content {
			.hero-header {
				text-align: left;
				font-size: 12vw;
				margin: 1rem 0;
				color: var(--neutral-very-dark-blue);
			}

			.hero-snippet {
				.hero-description {
					color: var(--neutral-grayish-blue);
					margin-top: 0;
					margin-bottom: 2rem;
				}

				.hero-cta {
					background: none;
					box-shadow: none;
					border: none;
					background-color: var(--primary-soft-red);
					padding: 0.5rem 2rem;
					font-size: 1rem;
					font-weight: 700;
					color: var(--neutral-off-white);
				}
			}
		}
	}

	// Styles for big screens
	@media (min-width: 769px) {
		.hero-container {
			margin: 0;
			display: grid;
			grid-template-columns: 1fr 1fr;
			grid-template-rows: 1fr 1fr;
			width: 100%;
			height: 100%;
			.hero-image {
				height: 100%;
				width: 100%;
				grid-row: 1/2;
				grid-column: 1/3;
			}

			.hero-content {
				grid-row: 2/3;
				grid-column: 1/3;
				display: grid;
				grid-template-columns: 1fr 1fr;

				.hero-header {
					font-size: 4vw;
					margin: 1rem 0 0 0;
				}

				.hero-snippet {
					.hero-description {
						margin: 2rem auto;
					}
				}
			}
		}
	}
</style>
