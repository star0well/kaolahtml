<template>
	<a href="" class="phone">
		<span>手机考拉</span>
		<span class="img">
			<img src="~@/assets/img/qrcode.png" style="width: 116px; height: 116x" />
			<span>新用户下载APP</span>
			<span>领取1000元红包</span>
		</span>
	</a>
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
.phone {
	position: relative;
	span:hover + .img {
		display: inline-block;
	}
	.img {
		position: absolute;
		display: none;
		text-align: center;
		background-color: #fff;
		z-index: 999;
		top: 30px;
		left: 0;
		transform: translate(-50%);
		margin-left: 50%;
		border: 1px solid red;
		line-height: 1.15;
		span {
			display: block;
		}
	}
}
</style>
