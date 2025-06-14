<template>
	<div>
		<h2>반응형 메시지</h2>
		<p>{{ reactiveMessage }}</p>
		<button v-on:click="addReactiveMessage">Add Message</button>
		<h2>일반 메시지</h2>
		<p>{{ normalMessage }}</p>
		<button onclick="addNormalMessage">Add Message</button>
	</div>
</template>

<script>
import { onBeforeMount, onMounted, ref } from 'vue';
export default {
	setup() {
		console.log('setup.');
		const reactiveMessage = ref('Hello Reactive Message');

		const addReactiveMessage = () => {
			reactiveMessage.value = reactiveMessage.value + '!';
		};
		let normalMessage = 'Hello Reactive Message';
		const addNormalMessage = () => {
			normalMessage = normalMessage + '!';
		};

		onMounted(() => {
			console.log('마운트되었습니다.');
		});
		onBeforeMount(() => {
			console.log('onBeforeMount.');
		});

		return {
			reactiveMessage,
			normalMessage,
			addReactiveMessage,
			addNormalMessage,
		};
	},
};
</script>

<style lang="scss" scoped></style>
