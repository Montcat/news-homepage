<template>
	<div class="desktop-nav-container">
		<div class="nav-item"><a href="#" class="nav-link">Home</a></div>
		<div class="nav-item"><a href="#" class="nav-link">New</a></div>
		<div class="nav-item"><a href="#" class="nav-link">Popular</a></div>
		<div class="nav-item"><a href="#" class="nav-link">Trending</a></div>
		<div class="nav-item"><a href="#" class="nav-link">Category</a></div>
	</div>
</template>

<script setup></script>

<style lang="scss" scoped>
	.desktop-nav-container {
		display: flex;
		gap: 3rem;
		justify-content: end;

		.nav-item {
			.nav-link {
				color: var(--neutral-grayish-blue);
				font-weight: 400;
			}

			.nav-link:hover {
				color: var(--primary-soft-red);
			}
		}
	}
</style>
