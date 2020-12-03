<template>
	<div>
		<tr>
			<TdComponent
				v-for="(data, index) in rowData"
				:key="index"
				:cellData="data"
				:cellIndex="index"
				:rowIndex="rowIndex"
			/>
		</tr>
	</div>
</template>
<script lang="ts">
import Vue from 'vue';
import TdComponent from './TdComponent';
export default Vue.extend({
	name: 'TrComponent',
	components: {
		TdComponent
	},
	props: {
		rowData: Array,
		rowIndex: Number
	}
});
</script>
