<template>
	<center>
		<div id="screen" @click="onChangeScreen" :class="state">
			<p>클릭해서 시작하세요</p>
		</div>
		<h1>평균 시간: {{}}</h1>
		<input type="button" value="리셋" />
	</center>
</template>

<script>
export default {
	name: 'App',
	data() {
		return {
			state: 'start'
		};
	},
	methods: {
		onChangeScreen() {
			switch (this.state) {
				case 'start':
					return (this.state = 'wait');
				case 'wait':
					return (this.state = 'go');
				case 'go':
					return (this.state = 'start');
				default:
					return (this.state = 'start');
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
