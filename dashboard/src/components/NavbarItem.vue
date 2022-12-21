<template>
	<a class="navbar-item" :href="link">
		<i :class="icon"></i>
	</a>
</template>

<script lang="ts">
export default {
	name: 'NavbarItem',
	props: {
		icon: String,
		link: String
	}
}
</script>

<style lang="scss" scoped>
.navbar-item {
	// Shape
	@apply h-full aspect-square;
	@apply flex justify-center items-center;

	// Appearance
	@apply cursor-pointer;

	&:hover {
		i {
			@apply text-neutral-400;
		}
	}

	i {
		// Shape
		@apply text-2xl;

		// Appearance
		@apply text-neutral-50;
	}
}
</style>