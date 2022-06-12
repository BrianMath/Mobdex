<template>
	<header>
		<h1>Mobdex</h1>

		<a href="#Top">
			<div v-for="mob in mobs" :key="mob.id" @click="changeMob(mob.id)">
				<img :src="mob.img" :alt="mob.name" loading="lazy">
				{{ mob.name }}
			</div>
		</a>
	</header>

	<main>
		<h1 id="Top">{{ mobName }}</h1>

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
					{id: 1, name: "Aldeão", img: "https://static.wikia.nocookie.net/minecraft_gamepedia/images/4/4a/VillagerFace.png", text: "Aldeão"},
					{id:2, name: "Allay", img: "https://static.wikia.nocookie.net/minecraft_gamepedia/images/8/81/AllayFace.png/", text: "Allay"},
					{id:3, name: "Axolote", img: "https://static.wikia.nocookie.net/minecraft_gamepedia/images/4/4a/AxolotlFace.png", text: "Axolote"},
					{id:4, name: "Bacalhau", img: "https://static.wikia.nocookie.net/minecraft_br_gamepedia/images/6/66/CodBody.png", text: "Bacalhau"},
					{id:5, name: "Baiacu", img: "https://static.wikia.nocookie.net/minecraft_br_gamepedia/images/f/fe/PufferfishFace.png", text: "Baiacu"},
					{id:6, name: "Burro", img: "https://static.wikia.nocookie.net/minecraft_gamepedia/images/9/99/DonkeyFace.png", text: "Burro"},
					{id:7, name: "Cavalo", img: "https://static.wikia.nocookie.net/minecraft_gamepedia/images/5/5e/HorseFace.png", text: "Cavalo"},
					{id:8, name: "Cavalo Esqueleto", img: "https://static.wikia.nocookie.net/minecraft_gamepedia/images/d/d5/SkeletonHorseFace.png", text: "Cavalo Esqueleto"},
					{id:9, name: "Coelho", img: "https://static.wikia.nocookie.net/minecraft_gamepedia/images/7/71/RabbitFace.png", text: "Coelho"},
					{id:10, name: "Coguvaca", img: "https://static.wikia.nocookie.net/minecraft_br_gamepedia/images/3/32/MooshroomFace.png", text: "Coguvaca"},
					{id:11, name: "Coguvaca Marrom", img: "https://static.wikia.nocookie.net/minecraft_gamepedia/images/2/22/BrownMooshroomFace.png", text: "Coguvaca Marrom"},
					{id:12, name: "Galinha", img: "https://static.wikia.nocookie.net/minecraft_br_gamepedia/images/5/53/ChickenFace.png", text: "Galinha"},
					{id:13, name: "Gato", img: "https://static.wikia.nocookie.net/minecraft_br_gamepedia/images/a/a2/CatFace.png", text: "Gato"},
					{id:14, name: "Girino", img: "https://static.wikia.nocookie.net/minecraft_gamepedia/images/5/5b/TadpoleFace.png", text: "Girino"},
					{id:15, name: "Golem de neve", img: "https://static.wikia.nocookie.net/minecraft_gamepedia/images/5/50/SnowGolemFace.png", text: "Golem de neve"},
					{id:16, name: "Jaguatirica", img: "https://static.wikia.nocookie.net/minecraft_br_gamepedia/images/6/60/OcelotFace.png", text: "Jaguatirica"},
					{id:17, name: "Lavagante", img: "https://static.wikia.nocookie.net/minecraft_gamepedia/images/5/55/StriderFace.png", text: "Lavagante"},
					{id:18, name: "Lula", img: "https://static.wikia.nocookie.net/minecraft_gamepedia/images/e/ea/SquidFace.png", text: "Lula"},
					{id:19, name: "Lula Brilhante", img: "https://static.wikia.nocookie.net/minecraft_gamepedia/images/1/15/GlowSquidFace.png", text: "Lula Brilhante"},
					{id:20, name: "Mula", img: "https://static.wikia.nocookie.net/minecraft_gamepedia/images/b/b0/MuleFace.png", text: "Mula"},
					{id:21, name: "Morcego", img: "https://static.wikia.nocookie.net/minecraft_br_gamepedia/images/2/2d/BatFace.png", text: "Morcego"},
					{id:22, name: "Ovelha", img: "https://static.wikia.nocookie.net/minecraft_br_gamepedia/images/b/b1/SheepFace.png", text: "Ovelha"},
					{id:23, name: "Papagaio", img: "https://static.wikia.nocookie.net/minecraft_br_gamepedia/images/3/37/ParrotFace.png", text: "Papagaio"},
					{id:24, name: "Peixe Tropical", img: "https://static.wikia.nocookie.net/minecraft_gamepedia/images/9/9f/TropicalFishBody.png", text: "Peixe Tropical"},
					{id: 25, name: "Porco", img: "https://static.wikia.nocookie.net/minecraft_br_gamepedia/images/0/03/PigFace.png", text: "O porco é o animal mais fofinho que existe e se procria com cenoura."},
					{id: 26, name: "Raposa", img: "https://static.wikia.nocookie.net/minecraft_br_gamepedia/images/8/88/FoxFace.png", text: "Raposa"},
					{id: 27, name: "Salmão", img: "https://static.wikia.nocookie.net/minecraft_br_gamepedia/images/2/2b/SalmonBody.png", text: "Salmão"},
					{id: 28, name: "Sapo", img: "https://static.wikia.nocookie.net/minecraft_gamepedia/images/0/0f/FrogFace.png", text: "Sapo"},
					{id: 29, name: "Tartaruga", img: "https://static.wikia.nocookie.net/minecraft_br_gamepedia/images/8/8b/TurtleFace.png", text: "Tartaruga"},
					{id: 30, name: "Vaca", img: "https://static.wikia.nocookie.net/minecraft_br_gamepedia/images/9/93/CowFace.png", text: "Vaca"},
					{id: 31, name: "Vendedor Ambulante", img: "https://static.wikia.nocookie.net/minecraft_br_gamepedia/images/8/83/WanderingTraderFace.png", text: "Vendedor Ambulante"},
					{id: 999, name: "Enderman", img: "https://i.pinimg.com/736x/e5/6e/19/e56e19905c0c4dc6cadba76ac765a96b--minecraft-mobs--life.jpg", text: "O Enderman é um cara alto e calado que pode ser encontrado em qualquer dimensão do jogo."},
				],
				mobName: 'Aldeão',
				mobImg: 'https://static.wikia.nocookie.net/minecraft_gamepedia/images/4/4a/VillagerFace.png',
				mobText: "Aldeão"
			}
		},
		methods: {
			changeMob(id) {
				this.mobs.forEach(mob => {
					if (mob.id == id) {
						this.mobName = mob.name
						this.mobImg = mob.img
						this.mobText = mob.text
						return
					}
				});
			}
		}
	}
</script>

<style>
	header {
		background-color: blue;
	}

	header h1 {
		text-align: center;
		padding: 10px;
	}

	main {
		background-color: red;
		display: flex;
		flex-direction: column;
		justify-content: flex-start;
		align-items: center;
	}

	header img {
		width: 50px;
		height: 50px;
		border-right: 5px solid #000;
		margin-right: 3px;
	}

	main img {
		width: 300px;
		height: 300px;
	}

	a, a:active, a:visited {
		color: #fff;
		text-decoration: none;
	}

	header div {
		display: flex;
		justify-content: flex-start;
		align-items: center;
		border: 2px solid black;
		margin-bottom: 2px;
	}

	header div:hover {
		color: #ffff00;
		font-weight: bold;
	}

	header div:active {
		text-decoration: underline;
	}
</style>