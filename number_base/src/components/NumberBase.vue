<template>
	<div>
		<form v-on:submit="onSubmit">
			<input type="text" v-model="value" />
			<input type="submit" />
		</form>
		<ul v-for="a in submit" v-bind:key="a">
			<li>{{ a }}</li>
		</ul>
		<p>{{ result }}</p>
	</div>
</template>
<script lang="ts">
const DrawNumber = () => {
	let waitNum = [1, 2, 3, 4, 5, 6, 7, 8, 9];
	let drawed = [];
	for (let i = 0; i < 4; i++) {
		drawed.push(waitNum.splice(Math.floor(Math.random() * waitNum.length), 1)[0]);
	}
	return drawed;
};
import Vue from 'vue';
export default Vue.extend({
	name: 'NumberBase',
	data() {
		return {
			test: '숫자야구',
			result: DrawNumber(),
			value: '',
			submit: []
		};
	},
	methods: {
		onSubmit(e) {
			e.preventDefault();
			let strike = 0;
			let ball = 0;
			for (let i = 0; i < 4; i++) {
				if (this.result[i] === Number(this.value[i])) {
					strike += 1;
				} else if (this.result.includes(Number(this.value[i]))) {
					ball += 1;
				}
			}
			this.submit.push(`${this.value} -  ${strike} 스트라이크 ${ball} 볼 입니다!`);
			this.value = '';
		}
	}
});
</script>
