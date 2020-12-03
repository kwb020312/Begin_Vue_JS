<template>
	<td style="width:20px;height:20px" @click="onClick">
		{{ cellData }}
	</td>
</template>
<script lang="ts">
import Vue from 'vue';
export default Vue.extend({
	name: 'TdComponent',
	props: {
		cellData: String,
		cellIndex: Number,
		rowIndex: Number
	},
	methods: {
		onClick() {
			this.$root.$data.turn = this.$root.$data.turn === 'O' ? 'X' : 'O';
			this.$set(this.$root.$data.table[this.rowIndex], this.cellIndex, this.$root.$data.turn);
		}
	}
});
</script>
