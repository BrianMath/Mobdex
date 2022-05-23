<template>
	<header>
		<h1>Mobdex</h1>

		<div v-for="mob in mobs" :key="mob.id" @click="changeMob(mob.id)">
			<img :src="mob.img" :alt="mob.name">
			{{ mob.name }}
		</div>
	</header>

	<main>
		<h1>{{ mobName }}</h1>

		<img :src="mobImg" :alt="mobName">

		<p>{{ mobText }}</p>
	</main>
</template>

<script>
	export default {
		name: 'App',
		data() {
			return {
				mobs: [
					{id: 1, name: "Porco", img: "https://i.pinimg.com/474x/58/05/bf/5805bfb974c92449a1c9335ebe58f009--minecraft-quilt-minecraft-room.jpg", text: "O porco é o animal mais fofinho que existe e se procria com cenoura."},
					{id: 2, name: "Enderman", img: "https://i.pinimg.com/736x/e5/6e/19/e56e19905c0c4dc6cadba76ac765a96b--minecraft-mobs--life.jpg", text: "O Enderman é um cara alto e calado que pode ser encontrado em qualquer dimensão do jogo."},
				],
				mobName: 'Porco',
				mobImg: 'https://i.pinimg.com/474x/58/05/bf/5805bfb974c92449a1c9335ebe58f009--minecraft-quilt-minecraft-room.jpg',
				mobText: "O porco é o animal mais fofinho que existe e se procria com cenoura."
			}
		},
		methods: {
			changeMob(id) {
				this.mobs.forEach(mob => {
					if (mob.id == id) {
						this.mobName = mob.name;
						this.mobImg = mob.img;
						this.mobText = mob.text;
					}
				});
			}
		}
	}
</script>

<style scoped>
	header {
		background-color: blue;
	}

	main {
		background-color: red;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
	}

	header, main {
		height: 100%;
	}

	header img {
		width: 50px;
		height: 50px;
	}

	main img {
		width: 300px;
		height: 300px;
	}

	header div {
		cursor: pointer;
		display: flex;
		justify-content: flex-start;
		align-items: center;
		border: 1px solid black;
		margin-bottom: 2px;
	}
</style>