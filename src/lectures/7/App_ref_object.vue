<template>
	<div></div>
</template>

<script>
import { ref, reactive } from 'vue';

export default {
	setup() {
		// ref => object
		const count = ref(0);
		const state = reactive({
			count,
		});

		count.value++;
		count.value++;

		console.log(count.value);
		console.log('state.count', state.count);
		// ref->array
		const message = ref('hello');
		const arr = reactive([message]);
		console.log('arr[0]', arr[0].value);
		return {};
	},
};
</script>
const arr
<style lang="scss" scoped></style>
