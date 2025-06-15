<template>
	<div>
		<button class="btn btn-primary" @click="$emit('createPost')">button</button>
	</div>
	자식컴포넌트에서 이벤트를 발생시키기 위해서는 컴포넌트의 인스턴스의 내장
	메소드인 emit을 사용할 수 있다.
</template>

<script>
export default {
	setup() {
		return {};
	},
};
</script>

<style lang="scss" scoped></style>
