<template>
	<div>
		<div>
			당첨번호들
			<div v-for="n in Nums" :key="n">
				<LottoBalls :number="n" />
			</div>
		</div>
		<input v-if="redo" type="button" @click="OnRedo" value="한번 더" />
	</div>
</template>

<script>
import LottoBalls from './components/LottoBalls';
const DrawNumbers = () => {
	let time = null;
	let AllNumbers = Array(45)
		.fill()
		.map((a, i) => i + 1);
	let Drawed = [];
	for (let i = 0; i <= 7; i++) {
		time = setTimeout(() => {
			Drawed.push(AllNumbers.splice(Math.floor(Math.random() * AllNumbers.length), 1)[0]);
		}, (i + 1) * 1000);
	}
	clearTimeout(time);
	return Drawed;
};
export default {
	name: 'App',
	components: {
		LottoBalls
	},
	data() {
		return {
			redo: false,
			Nums: DrawNumbers()
		};
	},
	methods: {
		OnRedo() {
			this.Nums = DrawNumbers();
			this.redo = false;
		}
	},
	mounted() {
		let time;
		time = setTimeout(() => {
			this.redo = true;
			clearTimeout(time);
		}, 7000);
	}
};
</script>
