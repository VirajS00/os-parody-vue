<template>
	<div class="container">
		<div class="trash" v-if="content.type == 'trash'">
			Nothing to see here, you’re not trash :)
		</div>
		<div class="folder" v-if="content.type == 'home'">
			home
		</div>
	</div>
</template>

<script>
export default {
	name: 'Contents',
	props: {
		content: Object
	},
	methods: {
		getImgUrl(img) {
			return require(`@/assets/icons/${img}`);
		}
	}
};
</script>

<style scoped>
.container {
	position: absolute;
	bottom: 0;
	right: 0;
	left: 25%;
	top: 3.2rem;
	border-bottom-right-radius: 3rem;
}

.trash {
	display: flex;
	flex-direction: column;
	justify-content: center;
	align-items: center;
	height: 100%;
	font-size: 1.1rem;
}
</style>
