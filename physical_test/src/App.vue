<template>
	<center>
		<div id="screen" :class="state">
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
	methods: {}
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
</style>
