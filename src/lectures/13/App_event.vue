<template>
	<div>
		<button @click="printEvnetInfo('Hello Vue3', $event)">
			inline event handler
		</button>
		<hr />
		<input type="text" v-on:keyup="onkeyupHandler" />
	</div>
</template>

<script>
export default {
	setup() {
		const printEvnetInfo = (message, event) => {
			console.log('message:', message);
			console.log('event.target: ', event.target);
			console.log('event.target.tagName: ', event.target.tagName);
		};
		const onkeyupHandler = event => {
			console.log('event.key: ', event.key);
		};
		return { printEvnetInfo, onkeyupHandler };
	},
};
</script>

<style lang="scss" scoped></style>
