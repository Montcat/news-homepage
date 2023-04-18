<template>
	<div class="app-container">
		<!-- header section -->
		<header>
			<div class="logo">
				<img src="./assets/images/svgs/logo.svg" alt="" />
			</div>

			<!-- Nav Section -->
			<nav>
				<div class="nav-container">
					<MobileNav v-if="!isLargeScreen" />
					<DesktopNav v-else />
				</div>
			</nav>
		</header>

		<!-- main section -->
		<main>
			<!-- Hero Section-->
			<section class="hero-section">
				<Hero />
			</section>

			<!-- News Section-->
			<section class="news-section">
				<News />
			</section>

			<!-- Top Articles Section-->
			<section class="popular-articles">
				<Popular />
			</section>
		</main>

		<!-- Footer section -->
		<footer>
			<Footer />
		</footer>
	</div>
</template>

<script setup>
	import MobileNav from "./components/navigation/MobileNav.vue";
	import DesktopNav from "./components/navigation/DesktopNav.vue";
	import Hero from "./components/hero/Hero.vue";
	import News from "./components/news-section/News.vue";
	import Popular from "./components/popular/Popular.vue";
	import Footer from "./components/Footer.vue";
	import { useMediaQuery } from "@vueuse/core";

	const isLargeScreen = useMediaQuery("(min-width: 769px)");
</script>

<style lang="scss" scoped>
	// Header Section
	.app-container > header {
		display: flex;
		justify-content: space-between;
		align-items: center;

		.logo {
			width: auto;

			img {
				width: 100%;
				height: 100%;
				object-fit: fill;
			}
		}

		nav {
			flex-grow: 1;
		}
	}

	// Styles for big screens
	@media (min-width: 769px) {
		.app-container > main {
			display: grid;
			grid-template-columns: 1fr 1fr 1fr;
			grid-template-rows: 18rem 18rem 18rem;
			grid-column-gap: 2rem;
			margin-top: 2rem;

			.hero-section {
				grid-column: 1/3;
				grid-row: 1/3;
			}

			.news-section {
				grid-column: 3/4;
				grid-row: 1/3;
			}

			.popular-articles {
				grid-row: 3/4;
				grid-column: 1/4;
			}
		}
	}
</style>
