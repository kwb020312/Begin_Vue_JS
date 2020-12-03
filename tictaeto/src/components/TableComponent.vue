<template>
	<div>
		<table border="1">
			<TrComponent v-for="(rowData, index) in table" :key="index" :rowData="rowData" :rowIndex="index" />
		</table>
	</div>
</template>
<script lang="ts">
import Vue from 'vue';
import TrComponent from './TrComponent';
export default Vue.extend({
	name: 'TableComponent',
	components: {
		TrComponent
	},
	props: {
		table: Array
	}
});
</script>
