<template>
	<div class="container" @click="UnSelectItem($event)">
		<div class="trash" v-if="content.type == 'trash'">
			Nothing to see here, you’re not trash :)
		</div>
		<ul class="folder" v-if="content.type == 'home'" ref="items">
			<li
				class="folder-container"
				v-for="{ id, name, icon } in items"
				:key="id"
				:class="{ selected: id === isSelected }"
				@click="selectItem(id)"
			>
				<img :src="getImgUrl(icon)" alt="Folder Icon" />
				<div class="name">{{ name }}</div>
			</li>
		</ul>
	</div>
</template>

<script>
import vClickOutside from 'v-click-outside';

export default {
	name: 'Contents',
	props: {
		content: Object
	},
	data() {
		return { items: [], isSelected: null };
	},
	mounted() {
		this.popupItem = this.$el;
		if (this.$props.folderContents !== []) {
			this.items = [...this.$props.content.folderContents];
		}
	},
	methods: {
		getImgUrl(img) {
			return require(`@/assets/icons/${img}`);
		},
		selectItem(i) {
			this.isSelected = i;
		},
		UnSelectItem(e) {
			if (this.$refs.items !== e.target) return;
			this.isSelected = null;
		}
	},
	directives: {
		clickOutside: vClickOutside.directive
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
	box-sizing: border-box;
	padding: 2.5rem;
	display: grid;
	grid-template-columns: repeat(auto-fit, minmax(60px, 1fr));
	gap: 2.5rem;
	height: 100%;
	width: 100%;
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

.folder-container div {
	position: relative;
}

.selected div::before {
	content: '';
	position: absolute;
	inset: 0 -1em;
	background-color: #5877c5;
	z-index: -1;
	border-radius: 100vw;
}
</style>
