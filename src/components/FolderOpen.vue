<template>
	<div class="folder">
		<div v-if="content === 'trash'">
			<TopBar text="Trash" img="trash.svg" />
			<Sidebar active="trash" />
			<Contents :content="tasks" />
		</div>
		<div v-if="content === 'home'">
			<TopBar text="Home" img="folder.svg" />
			<Sidebar active="home" />
			<Contents :content="tasks" />
		</div>
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
	props: {
		content: String
	},
	data() {
		return {
			tasks: {}
		};
	},
	created() {
		if (this.$props.content === 'trash') {
			this.tasks = {
				type: 'trash'
			};
		} else if (this.$props.content === 'home') {
			this.tasks = {
				type: 'home',
				folderContents: [
					{
						id: 1,
						name: 'Users',
						type: 'folder',
						icon: 'folder.svg'
					},
					{
						id: 2,
						name: 'Apps',
						type: 'folder',
						icon: 'folder.svg'
					},
					{
						id: 3,
						name: 'Sources',
						type: 'folder',
						icon: 'folder.svg'
					},
					{
						id: 4,
						name: 'hello.png',
						type: 'image',
						icon: 'photoIcon.svg'
					}
				]
			};
		}
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
