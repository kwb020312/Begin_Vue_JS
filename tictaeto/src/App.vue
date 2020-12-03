<template>
	<div>
		<TableComponent :table="table" />
		<h2>{{ turn }} 님의 턴 입니다.</h2>
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
			table: tableData,
			turn: 'O'
		};
	}
};
</script>
