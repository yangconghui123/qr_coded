<template>
	<view>
		<view class="text-center">
			<view class="ewmBox">
				<view class="ewmWhiteBox">
					<view>您的邀请码</view>
						<canvas class="ewmImg y_margin_st" canvas-id="couponQrcode"></canvas>
					<view class="fz24 y_margin_st">扫一扫二维码<br />
						面对面分享给您的好友吧</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	const qrCode = require('@/core/weapp-qrcode.js')
	export default {
		components: {
			langSwitch
		},
		data() {
			return {
			};
		},
		onLoad: function(option) {
			console.log(option)
			this.invite_code = option.invite_code;
			setTimeout(() => {
				this.couponQrCode()
			}, 50)
		},
		methods: {
			// 二维码生成工具
			couponQrCode() {
				new qrCode('couponQrcode', {
					text: "http://www.baidu.com",
					width: 100,
					height: 100,
					colorDark: "#333333",
					colorLight: "#FFFFFF",
					correctLevel: qrCode.CorrectLevel.H
				})
			}
		}
	}
</script>

<style lang="scss">
	page {
		background: #dcc9ff;
	}

	.ewmBox {
		width: 80%;
		margin: 60rpx auto;
		background: url(../../static/yl/kuang.png) center top no-repeat;
		background-size: 100% auto;
		padding: 28rpx;
		max-width: 700px;

		.ewmWhiteBox {
			background: $uni-bg-color;
			border-radius: 10rpx;
			padding: 32rpx;

			.ewmImg {
				width: 50%;
				left:30%;
				top:30rpx
			}
		}
	}
</style>
