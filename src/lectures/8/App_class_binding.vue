<template>
	<div>
		<div class="text" :class="[isActive ? ' : 'class', errClass]">
			텍스트입니다.
		</div>
		<button v-on:click="toggle">toggle</button>
		<button v-on:click="hasError = !hasError">toggleError</button>
	</div>
</template>

<script>
import { computed, ref } from 'vue';

export default {
	setup() {
		const isActive = ref(true);
		const hasError = ref(false);
		// const classObject = reactive({ active: isActive, 'text-danger': hasError });
		const classObject = computed(() => {
			return {
				active: isActive,
				'text-danger': hasError,
			};
		});

		const toggle = () => {
			isActive.value = !isActive.value;
			console.log('isActive.value', isActive.value);
		};
		const activeClass = ref('active');
		const errClass = ref('error');
		return { toggle, hasError, classObject, activeClass, errClass };
	},
};
</script>

<style scoped>
.active {
	font-weight: 900;
}
.text-danger {
	color: red;
}
</style>
