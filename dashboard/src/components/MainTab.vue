<template>
	<Tab>
		<TabItem title="Overview" @click-event="overview"><i class="fa-solid fa-circle-info mr-4"></i></TabItem>
		<TabItem title="Sensors" @click-event="sensors"><i class="fa-solid fa-temperature-three-quarters mr-4"></i></TabItem>
		<TabItem title="Monitor" @click-event="monitor"><i class="fa-solid fa-chart-column mr-4"></i></TabItem>
		<TabItem title="Logs" @click-event="logs"><i class="fa-solid fa-box mr-4"></i></TabItem>
	</Tab>
</template>

<script lang="ts">
import Tab from "./Tab.vue"
import TabItem from "./TabItem.vue"
// import Vue from "vue";

export default {
	name: 'TabMain',
	props: {

	},
	components: {
		Tab,
		TabItem
	},
	methods: {
		async overview() {
			await fetch("http://nyx.lan:5000/api/user1234")
				.then(response => response.json())
				.then(async dat => {
					var payload: Array<Object> = [];
					for (let i = 0; i < dat.sensors.length; ++i) {
						await fetch("http://nyx.lan:5000/api/user1234/" + dat.sensors[i].id)
							.then(response => response.json())
							.then(sensor => {
								payload.push({
									'id': sensor.id,
									'name': sensor.name,
									'online': sensor.online,
									'type': sensor.type,
									'value': sensor.value
								});
							});
					}
					return payload;
				})
				.then((payload) => {
					this.$emit('overview', payload);
				});
		},
		sensors() {
			let grid = document.getElementById('grid');
			let data = document.getElementById('data');
			if (grid !== null && data !== null) {
				data.style.display = 'none';
				grid.style.display = 'grid';
			};
		},
		monitor() {
			let grid = document.getElementById('grid');
			let data = document.getElementById('data');
			if (grid !== null && data !== null) {
				data.style.display = 'none';
				grid.style.display = 'grid';
			};
		},
		logs() {
			let grid = document.getElementById('grid');
			let data = document.getElementById('data');
			if (grid !== null && data !== null) {
				data.style.display = 'none';
				grid.style.display = 'grid';
			};
		}
	}
}
</script>

<style lang="scss">
</style>