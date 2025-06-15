<template>
	<div></div>
</template>

<script>
import { reactive, ref, watch } from 'vue';

export default {
	setup() {
		const x = ref(0);
		const y = ref(0);

		const obj = reactive({
			counter: 0,
		});

		// watch(
		// 	() => x.value + y.value,
		// 	(sum, oldValue) => {
		// 		console.log('sum: ', sum);
		// 		console.log('old value: ', oldValue);
		// 	},
		// );

		// watch([x, y], ([newX, newY], [oldX, oldY]) => {
		// 	console.log('newX :', newX, 'oldX: ', oldX);
		// 	console.log('newY :', newY, 'oldY: ', oldY);
		// });
		// watch(
		// 	() => obj.counter, // getter 함수로 변경해야지만 오브젝트안의 값이 반응형이 된다.
		// 	(oldValue, newValue) => {
		// 		console.log('newValue: ', newValue);
		// 	},
		// );
		watch(obj, (oldValue, newValue) => {
			console.log('newValue: ', newValue);
			console.log('oldValue: ', oldValue);
		});
		const person = reactive({
			name: '홍길동',
			age: 30,
			hobby: '운동',
			obj: {
				count: 0,
			},
		});

		// watch(person, (newValue, oldValue) => {
		// 	console.log('newValue: ', newValue);
		// 	console.log('oldValue: ', oldValue);
		// });
		watch(
			() => person.obj.count,
			newValue => {
				console.log('newValue: ', newValue);
			},
		);
		return { x, y, obj, person };
	},
};
</script>

<style lang="scss" scoped></style>
