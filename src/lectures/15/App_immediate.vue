<template>
	<div>
		<p>{{ message }}</p>
		<p>{{ reverseMessage }}</p>
	</div>
</template>

<script>
import { ref, watch } from 'vue';

export default {
	setup() {
		const message = ref('Hello Vue3');
		const reverseMessage = ref('');

		watch(
			message,
			newValue => {
				reverseMessage.value = newValue.split('').reverse().join('');
			},
			{ immediate: true },
		);
		return { message, reverseMessage };
	},
};
</script>

<style lang="scss" scoped></style>
