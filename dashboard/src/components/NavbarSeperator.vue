<template>
	<div :class="['navbar-seperator', expanding ? 'expanding' : 'mx-' + margin]"></div>
</template>

<script lang="ts">
export default {
	name: 'NavbarSeperator',
	props: {
		margin: {
			type: Number,
			default: 0
		},
		expanding: {
			type: Number,
			default: 0
		}
	}
}
</script>

<style lang="scss" scoped>
.navbar-seperator {
	// Shape
	@apply w-px h-4/5;

	// Appearance
	@apply bg-neutral-500;
}

.expanding {
	// Shape
	@apply mx-auto;

	// Appearance
	@apply invisible;
}
</style>