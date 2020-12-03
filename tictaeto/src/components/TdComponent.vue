<template>
	<div>
		<td>
			{{ cellData }}
		</td>
	</div>
</template>
<script lang="ts">
import Vue from 'vue';
export default Vue.extend({
	name: 'TdComponent',
	props: {
		cellData: String,
		cellIndex: Number,
		rowIndex: Number
	}
});
</script>
