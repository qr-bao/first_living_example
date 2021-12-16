<template>
	<view>
		<view class="bg">
			<view>
				
			</view>
			<view>
				
			</view>
		</view>
		<view class="top">
			
			<view>
				将实时点装入口袋
			</view>
			<view>
				成为WRHAN Writer会员，全年预计立省1000元
			</view>
			
		</view>
		
		<mid v-on:sendprice="getprice"></mid>
		
		<view class="buttonUl">
			<view>
				支付￥{{price}}立即开通
			</view>
			<!-- <view class="">
				VIP学生认证5折
			</view> -->
		</view>
		
		<view class="bottom">
			<view class="" style="color: #939393;">
				会员权益与服务指南
			</view>
		</view>


		
	</view>
</template>

<script>
	import mid from '../../componets/VIP/midLi.vue'
	export default {
		components:{
			mid
		},
		data() {
			return {
				price:'20'
			};
		},
		methods:{
			getprice(val){
				this.price = val;
			}
		}
	}
</script>

<style lang="less" scoped>
	.bg{
		top: 0;
		z-index:-99;
		width: 100%;
		position: absolute;
		:nth-child(1){
			height: 300rpx;
			width: 100%;
			background-color: #a1d9f1;
			background-image: linear-gradient(88deg, #a1d9f1 0%, #5d77ce 100%);
		}
		:nth-child(2){
			background-color: white;
			height: 200rpx;
			transform: rotate(-8deg);
			width: 200%;
			position: absolute;
			top: 290rpx;
			right: -80rpx;
		}

	}
	.top{
		color: white;
		:nth-child(1){
			margin: 50rpx 0;
		}
		>view{
			text-align: center;

		}
	}
	
	.buttonUl{
		color: #8f7868;
		display: flex;
		justify-content: space-around;
		:nth-child(1){
			font-weight: 600;
			padding: 0 80rpx;
			line-height: 100rpx;
			border-radius: 50rpx;
			background-color: #a1d9f1;
			background-image: linear-gradient(88deg, #a1d9f1 0%, #afcbfd 100%);
		}
		:nth-child(2){
			font-size: 28rpx;
			text-align: center;
			border-radius: 50rpx;
			padding: 15rpx 30rpx;
			width: 120rpx;
			background-color: #c9e0fa;
		}
	}
	
	.bottom{
		padding: 30rpx;
		:first-child{
			font-weight: 600;
		}
	}
</style>
