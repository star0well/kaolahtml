<template>
	<div class="contener">
		<div class="header">
			<div class="c-left">
				<span>考拉欢迎你！</span>
				<span>登录</span>
				<span>免费注册</span>
				<a href="">
					<span>手机考拉</span>
					<img src="~@/assets/img/qrcode.png" />
					<span>行用户下载领取1000元红包</span>
				</a>
			</div>
			<div class="c-right">
				<span>每日签到</span>
				<span>我的订单</span>
				<span>个人中心</span>
				<span>客服服务</span>
				<span>充值中心</span>
				<span>消费者权益</span>
				<span>更多</span>
				<span>视频类容</span>
			</div>
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
.header {
	position: absolute;
	left: 0;
	right: 0;
	margin: auto;
	width: 1090px;
	height: 30px;
	font-size: 12px;
	line-height: 30px;
	color: #999;
	display: flex;
	overflow: hidden;
	justify-content: space-between;

	span {
		padding-left: 8px;
		padding-right: 14px;
	}
}
.contener {
	width: 100%;
	height: 30px;
	position: relative;
	background-color: black;
}
</style>
