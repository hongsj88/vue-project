<template>
	<div>
		<form action="" @submit.prevent>
			<input type="text" v-model.lazy="title" placeholder="Title" />
			<textarea v-model.lazy="contents" placeholder="Contents"></textarea>
			<hr />
			<button @click="save(title, contents)">저장</button>
		</form>
	</div>
</template>

<script>
import { ref, watchEffect } from 'vue';

export default {
	setup() {
		const title = ref('');
		const contents = ref('');
		const save = (title, contents) => {
			console.log(` 저장되었습니다. Title : ${title}, contents : ${contents}`);
		};
		watchEffect(() => {
			console.log('watchEffects');
			save(title.value, contents.value);
			console.log(title.value);
			console.log(contents.value);
		});
		return { title, contents, save };
	},
};
</script>

<style lang="scss" scoped></style>
