<template>
	<div class="border border-neutral-500 shadow rounded-md p-4 m-2 min-w-min bg-neutral-900">
		<div class="animate-pulse flex space-x-4">
			<div class="rounded-full bg-neutral-700 h-10 w-10"></div>
			<div class="flex-1 space-y-6 py-1">
				<div class="h-2 bg-neutral-700 rounded"></div>
				<div class="space-y-3">
					<div class="grid grid-cols-3 gap-4">
						<div class="h-2 bg-neutral-700 rounded col-span-2"></div>
						<div class="h-2 bg-neutral-700 rounded col-span-1"></div>
					</div>
					<div class="h-2 bg-neutral-700 rounded"></div>
				</div>
			</div>
		</div>
	</div>
</template>

<script lang="ts">
export default {
	name: 'Placeholder',
	props: {

	}
}
</script>

<style lang="scss" scoped>
</style>