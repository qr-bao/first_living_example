<template>
	<view class="li">
		<view class="head">{{sendmessage.title}}</view>
		<view class="message">{{sendmessage.content}}</view>
	</view>
</template>

<script>
	export default {
		props:{
			sendmessage:Object
		},
		data() {
			return {
				news:{},
			}
		},
		methods: {
			
		}
	}
</script>

<style lang="less" scoped>
	.li{
		box-shadow: 0px 3px 6px rgba(0, 0, 0, 0.16);
		padding: 20rpx 30rpx;
		box-sizing: border-box;
		margin-bottom: 20rpx;
		.head{
			// color: red;
			font-weight: 600;
			font-size: 40rpx;
			margin-bottom: 10rpx;
		}
		.message{
			font-size: 38rpx;
			color: #333333;
			line-height: 60rpx;
		}
	}
</style>
