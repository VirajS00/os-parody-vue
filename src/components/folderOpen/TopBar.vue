<template>
	<div class="topBar">
		<img :src="require(`@/assets/icons/${img}`)" :alt="{ text }" />
		<p>{{ text }}</p>
	</div>
</template>

<script>
export default {
	name: 'TopBar',
	props: {
		text: String,
		img: String
	}
};
</script>

<style scoped>
.topBar {
	display: flex;
	width: 100%;
	height: 3.2rem;
	background-color: #1b2544;
	position: absolute;
	top: 0;
	left: 0;
	border-radius: 3rem 3rem 0 0;
	justify-content: center;
	align-items: center;
}
</style>
