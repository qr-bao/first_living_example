<template>
	<view class="wrapper">
		

		
		<view class="mid">
			<view class="li" :class="nums==index?'active':''" v-for="(item,index) in VIP" @click="midCil(index)">
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
		

		

		
	</view>
</template>

<script>
	export default{
		methods:{
			midCil(index){
				this.nums=index
				this.$emit('sendprice',this.VIP[index].price);
			}
		},
		data(){
			return{

				nums:0,
				VIP:[
					{
						text:'每篇文章',
						price:'20'
					},
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
					},
				]
			}
		}
	}
</script>

<style scoped lang="less">
	.wrapper{
		padding: 30rpx 30rpx 15rpx;
	}

	
	.mid{
		
		display: flex;
		justify-content: space-around;
		margin-top: 10rpx;
		
		.li{
			background-color: white;
			padding: 70rpx 0;
			border: 1px solid #d0dde1;
			border-radius: 5px;
			width: 200rpx;
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
	.active{
		background-color: #d3e4f6 !important;
	}
	
	.bottom{
		margin-top: 10rpx;
		font-size: 25rpx;
	}

</style>
