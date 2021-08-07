<template>
	<div id="app">
		<Desktop />
	</div>
</template>

<script>
import Desktop from './components/Desktop.vue';

export default {
	name: 'App',
	components: {
		Desktop
	}
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@400;700&display=swap');
#app {
	position: absolute;
	inset: 0 0 0 -1px;
}
</style>
