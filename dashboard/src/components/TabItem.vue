<template>
	<button class="tab-item">
		<slot/>
	</button>
</template>

<script lang="ts">
export default {
	name: 'TabItem',
	props: {

	}
}
</script>

<style lang="scss" scoped>
.tab-item {
	// Shape
	@apply w-full h-12;
	@apply my-2 px-2 py-1;
	@apply flex flex-row justify-center items-center;
	@apply rounded-sm;

	&:first-child {
		@apply mt-0;
	}

	&:last-child {
		@apply mb-0;
	}

	// Appearance
	@apply bg-neutral-700;
	@apply cursor-pointer;
	@apply shadow-md;
	@apply font-mono;
	@apply text-lg font-bold;

	&:hover {
		@apply bg-neutral-500;
	}

	&:active {
		@apply bg-neutral-600;
	}
}
</style>