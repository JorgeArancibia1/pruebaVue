<template>
	<div class="nav">
		<router-link to="/">Home</router-link> |
		<!-- <router-link to="/about">About</router-link> -->
		<router-view />
	</div>
</template>

<script>

export default {
	name: 'Nav',
	components: {},
};
</script>
