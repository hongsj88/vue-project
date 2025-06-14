<template>
	<div>
		<p>{{ message }}</p>
		<button v-on:click="addMessage">Click</button>
	</div>
</template>

<script>
import { ref } from 'vue';

export default {
	setup() {
		let message = ref('hello Vue!');

		const addMessage = () => {
			message.value = message.value + '!';
		};
		console.log('message: ', message.value);
		console.log('message type', typeof message.value);
		return { message, addMessage };
	},
};
</script>

<style lang="scss" scoped></style>
