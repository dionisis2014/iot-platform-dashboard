<template>
	<div v-if="vert" :class="'mx-2' + (expand ? ' border-l border-neutral-400 h-auto' : '')">
		<slot />
	</div>
	<div v-if="!vert" :class="'my-2' + (expand ? ' border-l border-neutral-400 w-auto' : '')">
		<slot />
	</div>
</template>

<script lang="ts">
export default {
	name: 'Seperator',
	props: {
		vert: {
			type: Boolean,
			default: false
		},
		expand: {
			type: Boolean,
			default: false
		}
	}
}
</script>

<style lang="scss" scoped>

</style>