<template>
	<Tab>
		<TabItem title="Overview" v-on:click="overview()"><i class="fa-solid fa-circle-info mr-4"></i></TabItem>
		<TabItem title="Sensors" v-on:click="sensors()"><i class="fa-solid fa-temperature-three-quarters mr-4"></i></TabItem>
		<TabItem title="Monitor" v-on:click="monitor()"><i class="fa-solid fa-chart-column mr-4"></i></TabItem>
		<TabItem title="Logs" v-on:click="logs()"><i class="fa-solid fa-box mr-4"></i></TabItem>
	</Tab>
</template>

<script lang="ts">
import Tab from "../components/Tab.vue"
import TabItem from "../components/TabItem.vue"

export default {
	name: 'TabMain',
	props: {

	},
	components: {
		Tab,
		TabItem
	},
	methods: {
		overview() {
			let grid = document.getElementById('grid');
			let data = document.getElementById('data');
			if (grid !== null && data !== null) {
				data.style.display = 'none';
				grid.style.display = 'grid';
				fetch("test.json")
					.then(response => response.json())
					.then(dat => {
						for (let i = 0; i < dat.sensors.length; ++i) {
							let node = document.createElement('div');
							node.textContent = "ID: " + dat.sensors[i].id + " Name: " + dat.sensors[i].name + " Type: " + dat.sensors[i].type + " Value: " + dat.sensors[i].value;
							data?.appendChild(node);
						}
						data.style.display = 'block';
						grid.style.display = 'none';
					});
			}
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

<style lang="scss" scoped>

</style>