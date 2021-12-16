<template>
	<view class="wrapper" @click="changevip">
		<view class="blur">
			
		</view>
		<view class="button">
			充值VIP即可查看
		</view>
		
		<view class="bottom">
		</view>
			
		<view class="occupied">
			
		</view>
	</view>
</template>

<script>
	export default{
		methods:{
			changevip(){
				console.log(1111);
				this.$emit('changevip');
			}
		}
	}
	
</script>

<style scoped lang="less">
	.blur{
		width: 100%;
		height: 90rpx;
	}
	.wrapper{
		background-image: linear-gradient(0deg,rgba(255,255,255,1) ,rgba(255,255,255,1),rgba(255,255,255,.5));
		//background-image: linear-gradient(0deg,#e66465, #9198e5);
		
		position: absolute;
		bottom: 0;
		width: 100%;
	}
	.button{
		
		width: 90%;
		margin: 0 auto 0;
		height: 120rpx;
		line-height: 120rpx;
		text-align: center;
		font-size: 35rpx;
		color: white;
		font-weight: 600;
		background-image: url(../../static/bottomButton.png);
		background-size: 100% 100%;
		
	}
	.bottom{
		margin: 0 auto;
		background-image: url(../../static/newsDetailsimg.png);
		background-size: 100% 100%;
		height: 190rpx;
		width: 90%;
		// font-weight: 600;
		// :nth-child(1){
		// 	text-align: center;
		// }
		// :nth-child(2){
		// 	image{
		// 		width: 25rpx;
		// 		height: 25rpx;
		// 		border: 1px solid #939391;
		// 		border-radius: 50%;
				
		// 	}
		// }
	}
	.occupied{
		height: 20rpx;
		width: 100%;
	}
</style>
