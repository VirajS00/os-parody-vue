<template>
	<div class="folder">
		<Sidebar active="trash" />
	</div>
</template>

<script>
import Sidebar from './folderOpen/Sidebar.vue';
export default {
	name: 'FolderOpen',
	components: {
		Sidebar
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
	transform: translate(-50%, -50%);
	border-radius: 3rem;
}
</style>
