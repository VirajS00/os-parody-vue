<template>
	<div class="desktop">
		<div class="trash-icon" @click="isSelected" :class="{ selected: isActive }">
			<img src="../assets/icons/trash.svg" />
			<span class="text">Trash</span>
		</div>
		<FolderOpen content="home" />
		<TaskBar />
	</div>
</template>

<script>
import FolderOpen from './FolderOpen.vue';
import TaskBar from './taskBar.vue';

export default {
	name: 'Desktop',
	components: {
		FolderOpen,
		TaskBar
	},

	data() {
		return { isActive: false };
	},
	methods: {
		isSelected() {
			this.isActive = !this.isActive;
		}
	}
};
</script>

<style scoped>
.desktop {
	background-image: url(../assets/wallpaper.png);
	background-size: cover;
	position: absolute;
	inset: 0;
	color: #fff;
	font-family: 'Poppins', sans-serif;
	padding: 2em;
}

.trash-icon {
	display: flex;
	flex-direction: column;
	height: fit-content;
	width: fit-content;
	align-items: center;
	font-size: 1.2rem;
}

.trash-icon img {
	margin-bottom: 0.5em;
	width: 50px;
	user-select: none;
}

.trash-icon span {
	user-select: none;
	cursor: default;
}

.selected {
	position: relative;
}

.selected::after {
	content: '';
	position: absolute;
	left: -1.1em;
	top: -0.4em;
	background-color: #07c3fc86;
	width: 180%;
	height: 110%;
	border-radius: 0.6em;
	outline: 1px dashed #1281a4;
	outline-offset: -0.5em;
}
</style>
