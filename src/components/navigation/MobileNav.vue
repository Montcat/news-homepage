<template>
	<div class="mobile-nav-container">
		<div class="menu-image">
			<img
				src="@/assets/images/svgs/icon-menu.svg"
				alt=""
				@click="openNav = true"
			/>
		</div>

		<Teleport to="body">
			<Transition name="slide-fade">
				<div class="menu-container" v-if="openNav">
					<div class="close-btn">
						<img
							src="/src/assets/images/svgs/icon-menu-close.svg"
							alt=""
							@click="openNav = false"
						/>
					</div>

					<div class="menu-content">
						<div class="menu-item"><a href="#">Home</a></div>
						<div class="menu-item"><a href="#">New</a></div>
						<div class="menu-item"><a href="#">Popular</a></div>
						<div class="menu-item"><a href="#">Trending</a></div>
						<div class="menu-item"><a href="#">Categories</a></div>
					</div>
				</div>
			</Transition>
		</Teleport>
	</div>
</template>

<script setup>
	import { ref } from "vue";

	const openNav = ref(false);
</script>

<style lang="scss" scoped>
	.menu-image {
		display: flex;
		justify-content: end;
	}
	.menu-container {
		position: absolute;
		top: 0;
		right: 0;
		background-color: var(--neutral-off-white);
		width: 65svw;
		display: flex;
		flex-direction: column;
		height: 100%;
		gap: 4rem;

		.close-btn {
			padding-right: 2svw;
			display: flex;
			align-self: end;
		}

		.menu-content {
			padding-left: 10svw;
			display: grid;
			gap: 2rem;
			font-weight: 400;

			.menu-item {
				a {
					text-decoration: none;
					transition: 0.4s;
					color: var(--neutral-very-dark-blue);
				}

				a:hover {
					color: var(--primary-soft-red);
				}
			}
		}
	}

	// Transition styling
	/*
  Enter and leave animations can use different
  durations and timing functions.
*/
	.slide-fade-enter-active {
		transition: all 0.3s ease-out;
	}

	.slide-fade-leave-active {
		transition: all 0.3s cubic-bezier(1, 0.5, 0.8, 1);
	}

	.slide-fade-enter-from,
	.slide-fade-leave-to {
		transform: translateX(20px);
		opacity: 0;
	}
</style>
