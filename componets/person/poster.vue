<template>
	<view class="wrapper">
		
		<view class="top">
			<view>
				商家会员
			</view>
			<view>
				宣传片、海报均可投放
			</view>
			<view>
				更多权益>
			</view>
		</view>
		
		<view class="mid">
			<view class="li" v-for="(item,index) in VIP">
				<view class="title">
					{{item.text}}
				</view>
				
				<view class="price">
					<view >
						￥
					</view>
					<view >
						{{item.price}}
					</view>
					
				</view>
				
			</view>
		</view>
		
		<view class="bottom">
			开通前阅读《会员服务协议》及《自动续费服务规则》
		</view>
		
	</view>
</template>

<script>
	export default{
		data(){
			return{
				VIP:[
					{
						text:'连续包月',
						price:'80'
					},
					{
						text:'连续包季',
						price:'300'
					},
					{
						text:'连续包年',
						price:'1000'
					}
				]
			}
		}
	}
</script>

<style scoped lang="less">
	.wrapper{
		background-size: 100% 100%;
		background-image: url(../../static/bg2.png);
		padding: 30rpx 30rpx 15rpx;
	}
	.top{
		display: flex;
		align-items: flex-end;
		flex-basis:1;
		justify-content: space-between;
		:nth-child(2){
			font-size: 25rpx;
			transform: translateX(-20rpx);
		}
		:nth-child(3){
			font-size: 30rpx;
			color: #a1a2a3;
		}
		
	}
	
	.mid{
		display: flex;
		justify-content: space-around;
		margin-top: 10rpx;
		
		.li{
			padding: 20rpx 0;
			border: 1px solid #5297f8;
			background-color: #d9f5fc;
			border-radius: 3px;
			width: 180rpx;
			.title{
				font-size: 25rpx;
				text-align: center;
				font-weight: 600;
			}
			.price{
				color: #d8b449;
				display: flex;
				justify-content: center;
				align-items: flex-end;
				view:nth-child(2){
					font-size: 50rpx;
				}
			}
		}
	}
	
	.bottom{
		margin-top: 10rpx;
		font-size: 25rpx;
	}
</style>
