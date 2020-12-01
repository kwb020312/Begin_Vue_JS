<template>
	<center>
		<div id="screen" @click="onChangeScreen" :class="state">
			<p>{{ message }}</p>
		</div>
		<h1>걸린 시간: {{ time }}초</h1>
	</center>
</template>

<script>
let startTime = 0;
let endTime = 0;
let run;
export default {
	name: 'App',
	data() {
		return {
			state: 'start',
			time: 0,
			message: '클릭해서 시작하세요.'
		};
	},
	methods: {
		onChangeScreen() {
			switch (this.state) {
				case 'start':
					this.state = 'wait';
					this.message = '초록색이 되면 클릭하세요';
					startTime = new Date();
					run = setTimeout(() => {
						this.state = 'go';
						this.message = '지금 클릭하세요!';
					}, Math.random() * 5000);
					break;
				case 'wait':
					this.state = 'start';
					this.message = '너무 성급하시군요!';
					clearTimeout(run);
					break;
				case 'go':
					this.state = 'start';
					this.message = '클릭해서 시작하세요.';
					endTime = new Date();
					this.time = ((endTime - startTime) / 1000).toFixed(2);
					break;
			}
		}
	}
};
</script>
<style scoped>
#screen {
	width: 30rem;
	height: 30rem;
	text-align: center;
}
.start {
	background-color: skyblue;
}
.wait {
	background-color: red;
}
.go {
	background-color: greenyellow;
}
</style>
