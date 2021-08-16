<template>
	<div class="topBar">
		<img :src="getImgUrl(img)" :alt="text" />
		<p>{{ text }}</p>
		<a href="#" class="close"></a>
	</div>
</template>

<script>
export default {
	name: 'TopBar',
	props: {
		text: String,
		img: String
	},
	methods: {
		getImgUrl(img) {
			return require(`@/assets/icons/${img}`);
		}
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

.topBar img {
	height: 20px;
	margin-right: 0.5rem;
}

.close {
	height: 15px;
	width: 15px;
	display: flex;
	background-color: #bd4141;
	position: absolute;
	right: 2rem;
	border-radius: 50%;
	justify-content: center;
	align-items: center;
	text-decoration: none;
}

.close::after {
	content: 'x';
	color: #860000;
	font-size: 0.8rem;
	opacity: 0;
}

.close:hover::after {
	opacity: 1;
}
</style>
