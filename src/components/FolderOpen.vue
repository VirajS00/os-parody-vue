<template>
	<div class="folder">
		<TopBar text="Trash" img="trash.svg" />
		<Sidebar active="trash" />
		<Contents :content="tasks" />
	</div>
</template>

<script>
import Sidebar from './folderOpen/Sidebar.vue';
import TopBar from './folderOpen/TopBar.vue';
import Contents from './folderOpen/Contents.vue';

export default {
	name: 'FolderOpen',
	components: {
		Sidebar,
		TopBar,
		Contents
	},
	data() {
		return {
			tasks: {}
		};
	},
	created() {
		this.tasks = {
			type: 'trash'
		};
	}
};
</script>

<style scoped>
.folder {
	height: 70vw;
	width: 90vw;
	max-width: 900px;
	max-height: 600px;
	background-color: #0e1325;
	position: absolute;
	top: 50%;
	left: 50%;
	transform: translate(-50%, -55%);
	border-radius: 3rem;
}
</style>
