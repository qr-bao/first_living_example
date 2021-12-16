<template>
	<view class="wrapper">
		<view class="top">
			
			<view class="">
				<image :src="headImg" mode=""></image>
				<view class="name">
					{{name}}
				</view>
			</view>
			<view class="">
				个人昵称
			</view>
			
		</view>
		
		<!-- <view class="bottom">
			
			<view class="">
				<view class="">
					{{attentionCount}}
				</view>
				<view class="">
					关注
				</view>
			</view>
			
			<view class="">
				<view class="">
					{{fans}}
				</view>
				<view class="">
					粉丝
				</view>
			</view>
			
			<view class="">
				<view class="">
					{{visitor}}
				</view>
				<view class="">
					访问
				</view>
			</view>
			
			<view class="">
				<view class="">
					{{rank}}
				</view>
				<view class="">
					排名
				</view>
			</view>
			
		</view>
		 -->
	</view>
</template>

<script>
	export default{
		data(){
			return{
				headImg:'../../static/1.jpg',
				name:'阿巴阿巴',
				attentionCount:'99',
				fans:'99',
				visitor:'120',
				rank:'53W+'
			}
		}
	}
</script>

<style scoped lang="less">
	.top{
		display: flex;
		justify-content: space-between;
		align-items: center;
		padding: 0 25rpx;
		font-size: 30rpx;
		:nth-child(1){
			display: flex;
			align-items: center;
			.name{
				margin-left: 0.5em;
				font-weight: 600;
				font-size: 40rpx;
			}
		}
		image{
			border: 1rpx solid #e2e1e1;
			width: 145rpx;
			height: 145rpx;
			border-radius: 50%;
		}
	}
	.bottom{
		margin-top: 5rpx;
		background-color: #f7fbfd;
		padding: 30rpx 20rpx;
		display: flex;
		justify-content: space-around;
		view{
			text-align: center;
		}
		>view :nth-child(1){
			font-size: 35rpx;
			font-weight: 600;
		}
		>view :nth-child(2){
			font-size: 30rpx;
			color: #a1a2a3;
		}


	}
</style>
