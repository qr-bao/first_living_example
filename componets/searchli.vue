<template>
	<view>
		<li>
			<image :src=sendinfo.url mode=""></image>
			<view>{{sendinfo.content}}</view>
			<!-- 小图标 气球 -->
			<i v-if="sendinfo.index<=5"></i>
		</li>
	</view>
</template>

<script>
	export default {
		props:{
			sendinfo:Object
		},
		data() {
			return {
				
			}
		},
		methods: {
			
		}
	}
</script>

<style lang="less" scoped>
	li {
		height: 100rpx;
		width: 100%;
		font-size: 35rpx;
		box-sizing: border-box;
		display: flex;
		justify-content: flex-start;
		align-items: center;

		>image {
			width: 50rpx;
			height: 50rpx;
			margin-right: 20rpx;
		}

		>view {
			white-space: nowrap;
			overflow: hidden;
			text-overflow: ellipsis;
		}

		>i {
			width: 50rpx;
			height: 50rpx;
			background: url(../static/biaozhi.png) no-repeat center/cover;
		}
	}
</style>
