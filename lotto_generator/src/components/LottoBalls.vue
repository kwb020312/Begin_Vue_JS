<template>
	<div :style="WhatColor">
		{{ number }}
	</div>
</template>

<script lang="ts">
import Vue from 'vue';
export default Vue.extend({
	name: 'LottoBalls',
	props: {
		number: Number
	},
	computed: {
		WhatColor() {
			if (this.number <= 10) {
				return 'background:red';
			} else if (this.number <= 20) {
				return 'background:orange';
			} else if (this.number <= 30) {
				return 'background:yellow';
			} else if (this.number <= 40) {
				return 'background:green';
			} else {
				return 'background:blue';
			}
		}
	}
});
</script>

<style scoped>
div {
	border: 1px solid black;
	border-radius: 100%;
	width: 20px;
	text-align: center;
	float: left;
	margin-right: 10px;
}
</style>
