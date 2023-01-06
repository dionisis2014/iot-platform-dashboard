<template>
	<Container :flood="true" class="p-2">
		<MainTab @overview="overview" @changeTab="showLoading"/>
		<Seperator :vert="true" :expand="true" />
		<Container :flood="true" :fill="true">
			<div class="main-loading" id="main-loading">
				<Placeholder />
				<Placeholder />
				<Placeholder />
				<Placeholder />
				<Placeholder />
				<Placeholder />
				<Placeholder />
				<Placeholder />
				<Placeholder />
				<Placeholder />
				<Placeholder />
				<Placeholder />
			</div>
			<div class="main-data" id="main-data">
				<MainSensor v-for="sensor in data" :key="sensor.id" :id="sensor.id" :name="sensor.name" :online="sensor.online" :type="sensor.type" :value="sensor.value">
				</MainSensor>
			</div>
		</Container>
	</Container>
</template>

<script lang="ts">
import MainTab from './MainTab.vue';
import Placeholder from './Placeholder.vue';
import Container from './Container.vue';
import Seperator from './Seperator.vue';
import MainSensor from './MainSensor.vue';
import { ref } from 'vue';

export default {
	name: 'Main',
	props: {
	},
	components: {
		MainTab,
		Placeholder,
		Container,
		Seperator,
		MainSensor
	},
	setup(props) {
		let data = ref<Object[]>([]);
		return { data };
	},
	methods: {
		showLoading() {
			let element: HTMLElement | null;
			element = document.getElementById('main-loading');
			if (element !== null)
				element.style.display = 'grid';
			element = document.getElementById('main-data');
			if (element !== null)
				element.style.display = 'none';
		},
		showData() {
			let element: HTMLElement | null;
			element = document.getElementById('main-loading');
			if (element !== null)
				element.style.display = 'none';
			element = document.getElementById('main-data');
			if (element !== null)
				element.style.display = 'grid';
		},
		async overview(dat: Object[]) {
			this.data.splice(0, this.data.length);
			this.data = this.data.concat(dat);
			this.showData();
		}
	}
}
</script>

<style lang="scss" scoped>
.main-data {
	// Shape
	@apply w-full;
	@apply hidden;
	@apply grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 2xl:grid-cols-6;
	grid-template-rows: repeat(auto-fit, 10rem);
}

.main-loading {
	// Shape
	@apply w-full;
	@apply grid;
	@apply grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 2xl:grid-cols-6;
	grid-template-rows: repeat(auto-fit, 10rem);
}
</style>