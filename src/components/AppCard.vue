<template>
	<div class="card">
		<div class="card-body">
			<!-- {{ $props }} optios api에서 컴포넌트인스턴스(this) 에 접근가능하다-->
			<span class="badge bg-secondary">{{ typeName }}</span>
			<h5 class="card-title red mt-2">{{ title }}</h5>
			<p class="card-text">
				{{ contents }}
			</p>
			<a href="#" class="btn" :class="isLikeClass" @click="toggleLike"
				>좋아요</a
			>
		</div>
		<!-- <br />
		{{ obj }} -->
	</div>
</template>

<script>
import { computed } from '@vue/reactivity';

export default {
	props: {
		type: {
			type: String,
			default: 'news',
			validator: value => {
				return ['news', 'notice'].includes();
			},
		},
		title: {
			type: String,
			required: true,
		},
		contents: {
			type: String,
			required: true,
		},
		isLike: {
			type: Boolean,
			default: false,
		},
		obj: {
			type: Object,
			default: () => {},
		},
	},
	emits: ['toggleLike'],
	setup(props, context) {
		// console.log(props.title);
		const isLikeClass = computed(() => {
			return props.isLike ? 'btn-danger' : 'btn-outline-danger';
		});
		const typeName = computed(() =>
			props.type === 'news' ? '뉴스' : '공지사항',
		);
		const toggleLike = () => {
			// props.isLike = !props.isLike;
			// props.obj.title = '김길동';
			context.emit('toggleLike');
		};
		return { isLikeClass, typeName, toggleLike };
	},
};
</script>
<style></style>
