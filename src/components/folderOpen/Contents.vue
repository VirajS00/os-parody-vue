<template>
	<div class="container">
		<div class="trash" v-if="content.type == 'trash'">
			Nothing to see here, you’re not trash :)
		</div>
		<ul class="folder" v-if="content.type == 'home'">
			<li
				class="folder-container"
				v-for="{ id, name, icon } in items"
				:key="id"
			>
				<img :src="getImgUrl(icon)" alt="Folder Icon" />
				<div class="name">{{ name }}</div>
			</li>
		</ul>
	</div>
</template>

<script>
export default {
	name: 'Contents',
	props: {
		content: Object
	},
	data() {
		return { items: [] };
	},
	mounted() {
		this.items = [...this.$props.content.folderContents];
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

.folder {
	padding: 2.5rem;
	display: grid;
	grid-template-columns: repeat(auto-fit, minmax(60px, 1fr));
	gap: 2.5rem;
}

.folder-container {
	display: flex;
	justify-content: center;
	align-items: center;
	flex-direction: column;
	width: fit-content;
	height: fit-content;
}

.folder-container img {
	height: 45px;
	margin-bottom: 0.7em;
}
</style>
