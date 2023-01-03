<template>
	<div :class="class_name">
		<slot />
	</div>
</template>

<script lang="ts">
export default {
	name: 'Container',
	props: {
		vert: {
			type: Boolean,
			default: false
		},
		expand: {
			type: Boolean,
			default: false
		},
		flood: {
			type: Boolean,
			default: false
		},
		fill: {
			type: Boolean,
			default: false
		}
	},
	setup(props) {
		let class_name: String = 'flex';
		if (props.vert) {
			class_name += ' flex-col';
			if (props.flood) {
				class_name += ' w-full h-full overflow-scroll';
			} else if (props.expand)
				class_name += ' h-full';
		} else {
			class_name += ' flex-row';
			if (props.flood) {
				class_name += ' w-full h-full overflow-scroll';
			} else if (props.expand)
				class_name += ' w-full';
		}
		if (props.fill)
			class_name += ' bg-neutral-600 rounded-sm p-2 shadow-md';
		return { class_name };
	}
}
</script>

<style lang="scss" scoped>

</style>