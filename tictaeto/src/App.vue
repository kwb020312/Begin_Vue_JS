<template>
	<div>
		<TableComponent :table="table" />
	</div>
</template>

<script>
import TableComponent from './components/TableComponent';
let tableData = [
	['', '', ''],
	['', '', ''],
	['', '', '']
];
export default {
	name: 'App',
	components: {
		TableComponent
	},
	data() {
		return {
			table: tableData
		};
	}
};
</script>
