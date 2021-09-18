<template>
	<div class="showData">
		<div class="c-left"></div>
		<div class="c-content">
			<a class="item" href="">
				<h3>斯凯奇新品上市</h3>
				<p>热门鞋款低至5.5折</p>
				<img src="@/assets/img/shoose.jpg" alt="" />
			</a>
			<div class="item">
				<h3>斯凯奇新品上市</h3>
				<p>热门鞋款低至5.5折</p>
				<img src="@/assets/img/shoose.jpg" alt="" />
			</div>
			<div class="item">
				<h3>斯凯奇新品上市</h3>
				<p>热门鞋款低至5.5折</p>
				<img src="@/assets/img/shoose.jpg" alt="" />
			</div>
			<div class="item">
				<h3>斯凯奇新品上市</h3>
				<p>热门鞋款低至5.5折</p>
				<img src="@/assets/img/shoose.jpg" alt="" />
			</div>
		</div>
		<div class="c-right">
			<a href="">11</a>
			<a href="">2</a>
			<a href="">3</a>
			<a href="">4</a>
			<span ref="spanRef" :class="{ rNav: !isFixed, fixed: isFixed }"
				><slot name="rNav"></slot
			></span>
		</div>
	</div>
</template>

<script lang="ts">
import { defineComponent, ref, computed } from 'vue';

export default defineComponent({
	components: {},
	props: {
		scrollTop: {
			type: Number,
			default: 0
		}
	},
	setup(props) {
		const spanRef = ref<HTMLElement>();
		const isFixed = computed(() => {
			return props.scrollTop > 676;
		});
		console.log(isFixed);
		console.log(props.scrollTop);

		return { spanRef, isFixed };
	}
});
</script>

<style scoped lang="less">
.showData {
	display: flex;
	width: 1090px;
	height: 541px;
	margin: 0 auto;
}
.c-left {
	width: 325px;
	height: 541px;
	background-color: blue;
}
.c-content {
	width: 554px;
	height: 541px;

	display: flex;
	flex-wrap: wrap;
	text-align: center;
	align-content: center;
	.item {
		width: 274px;
		height: 270px;
		h3 {
			font-weight: 400;
			font-size: 24px;
		}
		p {
			font-size: 14px;
		}
	}
}
.c-right {
	position: relative;
	background-color: #eaea;
	flex: 1;
	a {
		display: block;
		width: 219px;
		height: 120px;
		background-color: red;
	}
}
.rNav {
	position: absolute;
	right: -60px;
	top: 0;
}
.fixed {
	position: fixed;
	right: 50%;
	transform: translate(604px);
	top: 0;
}
</style>
