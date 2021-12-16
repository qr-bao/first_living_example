<template>
	<view>
		<view class="topIcon">
			<image src="../../static/saoyisao.png" mode=""></image>
			<image src="../../static/settings.png" mode=""></image>			
		</view>
		<personInfo></personInfo>
		
		<view class="midWind" @click="openCli">
			<view class="">
				<view class="">
					WRHAN Writer会员
				</view>
				<!-- <view class="">
					最低0.8元/天，享受免费下载，只能筛选热点内容等8项...
				</view> -->
			</view>
			<view class="rightButton">
				立即开通
			</view>
		</view>
		
		<VIP></VIP>
		<poster></poster>
		
		<view class="bottomButton">
			立即开通
		</view>
	</view>
</template>

<script>
	import personInfo from '../../componets/person/personInfo.vue'
	import VIP from '../../componets/person/VIP.vue'
	import poster from '../../componets/person/poster.vue'
	export default {
		methods:{
			openCli(){
				uni.navigateTo({
					url:'../VIP/VIP'
				})
			}
			
		},
		components:{
			personInfo,
			VIP,
			poster
		},
		data() {
			return {
				
			};
		}
	}
</script>

<style lang="less" scoped>
	
	.topIcon{
		padding: 20rpx;
		justify-content: space-between;
		display: flex;
		image{
			width: 50rpx;
			height: 45rpx;
		}
	}
	
	.midWind{
		display: flex;
		align-items: center;
		justify-content: space-around;
		background-image: url('../../static/bg2.png');
		background-size: 100% 100%;
		width: 90%;
		margin: 15rpx auto 0;
		padding: 30rpx 30rpx 25rpx;
		>view{
			:nth-child(1){
				font-size: 35rpx;
				font-weight: 600;
				margin-bottom: 10rpx;
			}
			:nth-child(2){
				font-size: 20rpx;
			}
		}
		.rightButton{
			background-image: url(../../static/openButton.png);
			background-size: 100% 100%;
			padding: 15rpx 25rpx;
			font-size: 30rpx;
			line-height: 50rpx;
			font-weight: 600;
			color: #5b2900;
		}
	}
	
	.bottomButton{
		width: 80%;
		margin: 0 auto;
		text-align: center;
		background-image: url('../../static/bottomButton.png');
		background-size: 100% 100%;
		padding: 30rpx 0;
	}
</style>
