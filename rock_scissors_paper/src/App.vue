<template>
	<center>
		<div
			:style="{
				background: `url(https://en.pimg.jp/023/182/267/1/23182267.jpg) ${coord} 0`,
				width: '142px',
				height: '200px'
			}"
		></div>
		<input @click="onResult('바위')" type="button" value="바위" />
		<input @click="onResult('가위')" type="button" value="가위" />
		<input @click="onResult('보')" type="button" value="보" />
		<h2>{{ result }}</h2>
	</center>
</template>

<script>
const Dictionary = {
	바위: '0',
	가위: '-142px',
	보: '-284px'
};
const Cal = {
	가위: -1,
	바위: 0,
	보: 1
};
const ComPick = (addr) => {
	return Object.entries(Dictionary).filter((a) => a[1] === addr)[0];
};
let ChangePic = null;
export default {
	name: 'App',
	data() {
		return {
			coord: Dictionary.바위,
			result: '선택해주세요 !'
		};
	},
	methods: {
		onResult(addr) {
			const score = Cal[addr] - Cal[ComPick(this.coord)[0]];
			if (score === -1 || score === 2) {
				this.result = '졌습니다 ㅜㅜ';
			} else if (score === 0) {
				this.result = '비겼습니다.';
			} else {
				this.result = '이겼습니다!';
			}
			clearInterval(ChangePic);
			setTimeout(() => {
				this.Change();
			}, 1000);
		},
		Change() {
			ChangePic = setInterval(() => {
				if (this.coord === Dictionary.바위) {
					this.coord = Dictionary.가위;
				} else if (this.coord === Dictionary.가위) {
					this.coord = Dictionary.보;
				} else if (this.coord === Dictionary.보) {
					this.coord = Dictionary.바위;
				}
			}, 100);
		}
	},
	mounted() {
		this.Change();
	},
	destroyed() {
		clearInterval(ChangePic);
	}
};
</script>

<style></style>
