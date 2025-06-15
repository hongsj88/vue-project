<template>
	<div>
		<div v-memo="[subscribes, views]">
			<p>subscribes : {{ subscribes }}</p>
			<p>views : {{ views }}</p>
			<p>likes : {{ likes }}</p>
		</div>
		<button @click="subscribes++">Subs++</button>
		<button @click="views++">views++</button>
		<button @click="likes++">likes++</button>
		<div>
			<p>subscribes : {{ subscribes }}</p>
			<p>views : {{ views }}</p>
			<p>likes : {{ likes }}</p>
		</div>
	</div>
</template>

<script>
import { ref } from 'vue';

export default {
	setup() {
		const subscribes = ref(4000);
		const views = ref(400);
		const likes = ref(20);

		return { subscribes, views, likes };
	},
};
</script>

<style lang="scss" scoped></style>
