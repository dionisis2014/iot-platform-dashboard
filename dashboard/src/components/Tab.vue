<template>
	<div class="tab">
		<slot/>
	</div>
</template>

<script lang="ts">
export default {
	name: 'Tab',
	props: {

	}
}
</script>

<style lang="scss" scoped>
.tab {
	// Shape
	@apply w-1/6;
	@apply overflow-scroll;
}
</style>