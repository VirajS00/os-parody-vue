<template>
	<div class="taskBar">
		<img
			src="@/assets/icons/appMenu.svg"
			alt="App Menu"
			class="icon"
			style="height: 40px;"
		/>
		<form action="">
			<input type="text" class="searchbox" placeholder="Your Search Query..." />
		</form>

		<div class="appIcon active">
			<img src="@/assets/icons/folder.svg" alt="App Menu" class="icon" />
		</div>
		<div class="appIcon">
			<img src="@/assets/icons/terminal.svg" alt="App Menu" class="icon" />
		</div>
		<div class="appIcon">
			<img src="@/assets/icons/settings.svg" alt="App Menu" class="icon" />
		</div>
		<div class="appIcon">
			<img src="@/assets/icons/browser.svg" alt="App Menu" class="icon" />
		</div>
		<div class="appIcon">
			<img src="@/assets/icons/info.svg" alt="App Menu" class="icon" />
		</div>
	</div>
</template>

<script>
export default {
	name: 'taskBar'
};
</script>

<style scoped>
.taskBar {
	position: absolute;
	bottom: 1rem;
	left: 1rem;
	right: 1rem;
	background-color: rgb(0, 0, 0, 0.8);
	height: 3rem;
	border-radius: 100vw;
	color: #fff;
	display: flex;
	align-items: center;
	padding: 0 0.3em;
	gap: 1.5rem;
}

.icon {
	height: 32px;
	position: relative;
}

.searchbox {
	background-color: rgb(45, 62, 87, 0.7);
	border: 0;
	font-size: 1rem;
	padding: 0.4em 1.3em;
	width: 350px;
	outline: none;
	border-radius: 100vw;
	color: #fff;
	transition: background-color 250ms ease;
}

.searchbox:focus {
	background-color: rgba(31, 43, 62, 0.7);
}

::placeholder {
	color: #98bbef;
}

::-moz-placeholder {
	color: #98bbef;
}

::-webkit-input-placeholder {
	color: #98bbef;
}

.appIcon {
	height: 100%;
	display: flex;
	justify-content: center;
	align-items: center;
	position: relative;
	z-index: 1;
}

.appIcon.active::after {
	content: '';
	position: absolute;
	inset: 0 -0.5rem;
	background-color: rgb(21, 75, 216, 0.4);
	border-bottom: 0.3em solid #3f6ad9;
	z-index: -1;
}
</style>
