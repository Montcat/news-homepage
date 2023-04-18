<template>
	<div class="footer-container">
		<p class="content">
			<span class="footer-item">
				Challenge by:
				<a href="https://www.frontendmentor.io">Frontend Mentor</a>.
			</span>
			<span class="footer-item">
				Created by: <a href="https://www.frontendmentor.io/home">Mont King</a>.
			</span>
		</p>
	</div>
</template>

<script setup></script>

<style lang="scss" scoped>
	.footer-container {
		display: flex;
		justify-content: center;

		.content {
			.footer-item {
				a {
					color: var(--neutral-very-dark-blue);
				}

				a:hover {
					color: var(--primary-soft-red);
				}
			}
		}
	}
</style>
