<template>
	<div class="contener">
		<div class="header">
			<div class="c-left">
				<span>考拉欢迎你！</span>
				<span>登录</span>
				<span>免费注册</span>
				<yc-dropdown />
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
import YcDropdown from '@/base-ui/dropdown/index';

export default defineComponent({
	components: {
		YcDropdown
	},
	setup() {
		return {};
	}
});
</script>

<style scoped lang="less">
.header {
	margin: 0 auto;
	width: 1090px;
	height: 30px;
	line-height: 30px;
	font-size: 12px;

	color: #999;
	display: flex;

	justify-content: space-between;
	.c-right {
		span {
			padding-left: 8px;
			padding-right: 14px;
		}
	}
	.c-left {
		span {
			margin-right: 30px;
		}
	}
}
.contener {
	width: 100%;
	height: 30px;
	position: relative;
	background-color: black;
}
</style>
