<template>
	<div></div>
</template>

<script>
import { ref, watch } from 'vue';

export default {
	setup() {
		const message = ref('');

		watch(message, (newValue, oldValue) => {
			console.log('new value:', newValue);
			console.log('old value:', oldValue);
		});
		return { message };
	},
};
</script>

<style lang="scss" scoped></style>
