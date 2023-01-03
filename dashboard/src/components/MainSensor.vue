<template>
	<div class="main-sensor">
		<div class="main-sensor-info">
			<span class="main-sensor-key">ID: </span><span class="main-sensor-value">{{ id }}</span>
		</div>
		<div class="main-sensor-info">
			<span class="main-sensor-key">Name: </span><span class="main-sensor-value">{{ name }}</span>
		</div>
		<div class="main-sensor-info">
			<span class="main-sensor-key">Online: </span><i :class="'main-sensor-value fa-solid fa-circle ' + (online ? 'text-green-600' : 'text-red-600')"></i>
		</div>
		<div class="main-sensor-info">
			<span class="main-sensor-key">Type: </span><i :class="getTypeIcon() + ' main-sensor-value'"></i>
		</div>
		<div class="main-sensor-info">
			<span class="main-sensor-key">Value: </span><span class="main-sensor-value">{{ value }}</span>
		</div>
	</div>
</template>

<script lang="ts">
export default {
	name: 'MainSensor',
	props: {
		id: String,
		name: String,
		online: Boolean,
		type: String,
		value: Number
	},
	methods: {
		getTypeIcon() {
			if (this.type === 'temp') {
				return "fa-solid fa-temperature-three-quarters";
			} else if (this.type === 'humid') {
				return "fa-solid fa-droplet";
			} else if (this.type === 'light') {
				return "fa-solid fa-circle-half-stroke";
			} else if (this.type === 'winds') {
				return "fa-solid fa-wind";
			} else if (this.type === 'windd') {
				return "fa-solid fa-compass";
			} else {
				return "fa-regular fa-circle-question";
			}
		}
	}
}
</script>

<style lang="scss" scoped>
.main-sensor {
	// Shape
	@apply flex flex-col justify-center items-start;
	@apply m-2 p-2 rounded-md min-w-min;
	@apply cursor-pointer;

	// Appearance
	@apply bg-neutral-900;
	@apply border border-neutral-500 shadow-md;
	@apply transition-transform ease-in-out duration-200;

	&:hover {
		@apply scale-105 z-10 relative;
		@apply bg-neutral-800;
	}

	&:active {
		@apply bg-neutral-700;
	}
}

.main-sensor-info {
	// Shape
	@apply flex flex-row justify-center items-center;
	@apply w-full h-full;
}
.main-sensor-key {
	// Shape
	@apply inline-block;
	@apply mr-2;

	// Appearance

}

.main-sensor-value {
	// Shape
	@apply inline-block;
	@apply ml-auto;

	// Appearance
}
</style>