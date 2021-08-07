<template>
	<div class="sidebar">
		<div>
			<input
				type="text"
				name=""
				id=""
				placeholder="Your search query..."
				class="inp"
			/>
			<div style="margin-top: 2rem;">
				<div class="sidebar-el" :class="{ active: active === 'trash' }">
					<a href="">
						<img src="../../assets/icons/trash.svg" alt="Trash icon" />
						<p>Trash</p>
					</a>
				</div>
				<div class="sidebar-el" :class="{ active: active === 'home' }">
					<a href="">
						<img
							src="../../assets/icons/folder.svg"
							alt="Folder icon"
							style="height: 15px;"
						/>
						<p>Home</p>
					</a>
				</div>
			</div>
		</div>
	</div>
</template>

<script>
export default {
	name: 'Sidebar',
	props: {
		active: String
	}
};
</script>

<style scoped>
.sidebar {
	position: absolute;
	left: 0;
	top: 0;
	height: 100%;
	width: 25%;
	background-color: #18213f;
	border-radius: 3rem 0 0 3rem;
	display: flex;
	justify-content: center;
	padding-top: 5rem;
}

.sidebar-el {
	position: relative;
	z-index: 1;
}

.sidebar-el a {
	display: flex;
	justify-content: center;
	align-items: center;
	color: #fff;
	text-decoration: none;
}

.sidebar-el img {
	height: 22px;
	margin-right: 1em;
}

.sidebar-el:hover::after {
	content: '';
	position: absolute;
	top: 0.3em;
	left: 0;
	height: 80%;
	width: 100%;
	background-color: hsla(220, 55%, 32%, 0.4);
	border-radius: 100vw;
	pointer-events: none;
}

.sidebar-el.active::before {
	content: '';
	position: absolute;
	top: 0.3em;
	left: 0;
	height: 80%;
	width: 100%;
	background-color: rgb(20, 38, 72);
	border-radius: 100vw;
	pointer-events: none;
	z-index: -1;
}

.sidebar-el.active:hover::after {
	content: none;
}

.inp {
	background-color: #394777;
	border: 0;
	padding: 0.5rem 1.3rem;
	outline: none;
	color: #fff;
	border-radius: 100vw;
	transition: background-color 150ms ease;
	font-size: 1rem;
}

.inp:focus {
	background-color: #2e3757;
}

::placeholder {
	color: #5f81b6;
}
</style>
