<template>
	<div class="article-container">
		<a href="#" class="article-header">
			{{ articleHeader }}
		</a>

		<p class="article-content">
			{{ articleContent }}
		</p>
	</div>
</template>

<script setup>
	defineProps(["articleHeader", "articleContent"]);
</script>

<style lang="scss" scoped>
	.article-container {
		.article-header {
			font-weight: 800;
			color: var(--neutral-off-white);
		}

		.article-header:hover {
			color: var(--primary-soft-orange);
		}

		.article-content {
			color: var(--neutral-grayish-blue);
		}
	}
</style>
