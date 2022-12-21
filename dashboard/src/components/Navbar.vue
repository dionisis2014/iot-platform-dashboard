<template>
	<div class="navbar">
		<NavbarItem icon="fa-solid fa-house-user" link="#"/>
		<NavbarSeperatorVue link="#"/>
		<NavbarItem icon="fa-solid fa-inbox" link="#"/>
		<NavbarSeperatorVue link="#"/>
		<NavbarItem icon="fa-solid fa-globe" link="#"/>
		<NavbarSeperatorVue :expanding="1" />
		<NavbarItem icon="fa-solid fa-circle-user" link="#"/>
	</div>
</template>

<script lang="ts">
import NavbarItem from "../components/NavbarItem.vue"
import NavbarSeperatorVue from "./NavbarSeperator.vue";
export default {
	name: 'Navbar',
	components: {
		NavbarItem,
		NavbarSeperatorVue
	}
}

</script>

<style lang="scss" scoped>
.navbar {
	// Shape
	@apply w-full h-12;
	@apply flex flex-row justify-start items-center;

	// Appearance
	@apply bg-neutral-700;
	@apply shadow-md;
}
</style>