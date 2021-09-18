<template>
	<div class="logoSearch">
		<div class="content">
			<a href="">
				<img src="~@/assets/img/kaolaLogo.png" alt="" />
			</a>
			<div class="topSearch"><input type="text" /><span></span></div>
			<div class="shop"></div>
		</div>
	</div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
	setup() {
		return {};
	}
});
</script>

<style scoped lang="less">
.logoSearch {
	position: relative;
	width: 100%;
	height: 100px;
}
.content {
	position: absolute;
	display: flex;
	align-items: center;
	width: 1090px;
	height: 100px;
	left: 0;
	right: 0;
	margin: auto;
}
.topSearch {
	display: flex;
	position: relative;
	align-items: center;
	left: 80px;
	width: 511px;
	height: 40px;
	border: 1px solid red;
	border-radius: 40px;
}
input {
	position: absolute;
	border: 0;
	outline: medium;
	width: 410px;
	height: 24px;
	left: 24px;
	line-height: 24px;
}
span {
	position: absolute;

	border-radius: 42px;
	right: -1px;
	width: 60px;
	height: 42px;
	background-color: red;
}
.shop {
	position: absolute;
	right: 76px;
	width: 106px;
	height: 36px;
	border-radius: 36px;
	border: 2px solid #ff1e32;
}
</style>
