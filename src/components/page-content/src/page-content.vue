<template>
	<div class="page-content">
		<div class="header">
			<span>所有分类</span>
			<a href="">首页</a>
			<a href="">海外直购</a>
			<a href="">考拉海购出品</a>
			<a href="">品质奶粉</a>
			<a href="">人气面膜</a>
			<a href="">充值</a>
		</div>
		<div class="content">
			<a href="" class="content-img">
				<img src="@/assets/img/content.jpg" alt="" />
				<span class="control">
					<i class="prev">向前</i>
					<i class="next">向右</i>
				</span>
			</a>
			<div class="list-data" @mouseleave="handleLeave">
				<div>
					<li @mouseenter="handlehover(0)" class="category">美容分类</li>
					<li @mouseenter="handlehover(1)" class="children">母婴儿童</li>
					<li @mouseenter="handlehover(0)">营养保健</li>
					<li @mouseenter="handlehover(0)">数码家电</li>
					<li @mouseenter="handlehover(0)">户外运动</li>
					<li @mouseenter="handlehover(0)">美容分类</li>
					<li @mouseenter="handlehover(0)">母婴儿童</li>
					<li>营养保健</li>
					<li>数码家电</li>
					<li>户外运动</li>
					<li>户外运动</li>
					<li>户外运动</li>
				</div>

				<div class="data" ref="divRef">
					<show-data :data="data" :currentIndex="currentIndex"></show-data>
				</div>
			</div>
			<div class="footer">
				<div class="wrap"></div>
				<div class="center">
					<ul>
						<li>考拉自营</li>
						<li>全球直采</li>
						<li>假一赔十</li>
						<li>售后无忧</li>
					</ul>

					<ul>
						<li>考拉自营</li>
					</ul>
				</div>
			</div>
		</div>
	</div>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';
import showData from './cps/showData.vue';

export default defineComponent({
	components: {
		showData
	},
	setup() {
		const divRef = ref<HTMLElement>();
		const currentIndex = ref(0);
		const handlehover = (index: number) => {
			currentIndex.value = index;
			if (divRef.value) {
				divRef.value.style.display = 'block';
				divRef.value.style.zIndex = '99';
			}
			return currentIndex;
		};
		const handleLeave = () => {
			setTimeout(() => {
				if (divRef.value) {
					divRef.value.style.display = 'none';
				}
			}, 100);
		};

		const data = [
			['洁面', '洗手液', '洁面', '洗手液', '洁面', '洗手液'],
			['奶粉 ', '纸尿裤']
		];
		return { handlehover, data, currentIndex, divRef, handleLeave };
	}
});
</script>

<style scoped lang="less">
.header {
	position: relative;
	display: flex;
	align-items: center;
	left: 0;
	right: 0;
	margin: auto;
	width: 1090px;
	height: 40px;

	span {
		width: 164px;
		height: 40px;
		line-height: 40px;
		text-align: center;
		background-color: #ff5160;
	}
	a {
		color: black;
		margin: 0 20px;
	}
}
.content {
	position: relative;
	display: flex;

	min-width: 1090px;
	a {
		z-index: 9;
		transform: translate(-50%);
		margin-left: 50%;
		img {
			vertical-align: bottom;
		}
		.control {
			position: absolute;
			display: none;
			justify-content: space-between;
			text-align: center;
			line-height: 68px;
			left: 100px;
			right: 0;
			margin: 0 auto;
			top: 40%;
			height: 68px;
			width: 850px;

			i {
				display: inline-block;
				width: 34px;
				height: 68px;
				background-color: #eaea;
			}
		}
	}
}
.content-img:hover {
	.control {
		display: flex;
	}
}

.list-data {
	position: absolute;
	z-index: 99;
	display: flex;
	flex-direction: column;
	justify-content: space-between;
	left: 0;
	right: 0;
	margin: auto;
	height: 506px;
	width: 1090px;

	li {
		text-align: center;

		line-height: 38px;
		height: 36.5px;
		width: 164px;
		background: linear-gradient(90deg, red, #ff3264);
		border: 1px solid rgb(255, 81, 96);
	}
}
.data {
	display: none;
	position: absolute;
	z-index: -1;
	left: 164px;
	width: 926px;
	height: 506px;
	background-color: #fff;
}
.footer {
	overflow: hidden;
	display: flex;
	position: absolute;
	bottom: 0;
	height: 45px;
	width: 100%;

	.wrap {
		position: absolute;

		top: 0;
		bottom: 0;
		right: 0;
		left: 0;
		background: url('~@/assets/img/content.jpg') center bottom;
		filter: blur(5px);
	}
}
.center {
	z-index: 99;
	width: 1090px;
	height: 45px;
	margin: 0 auto;
	display: flex;
	justify-content: space-between;

	ul {
		display: flex;
		padding-left: 0px;
	}
}
</style>
