<template>
	<view class="wrapper lock">
		<view class="" style="margin: 40rpx auto; text-align: center; font-size: 6Z0rpx; font-weight: 600;">
			{{title}}
		</view>
		<view ref="id">
			{{sendcontext}}
		</view>
	</view>
</template>

<script>
	export default{
		props:{
			sendcontext:{
				require:true,
			}
		},
		watch:{
			sendcontext(val){
				let title = uni.getStorageSync('title');
				this.title = title;
				let con = this.$refs.id;
				console.log(con)
			}
		},
		onLoad() {
			
		},
		data(){
			return{
				title:'',
			}
		},
	}
</script>

<style scoped lang="less">
	.wrapper{
		width: 718rpx;
		margin: 25rpx auto;Z
		background-color: #dee8f1;
		min-height: 900rpx;
		border-radius: 15px;
		
	}
	.lock{
		// max-height: 900rpx;
		overflow: hidden;
		font-size: 38rpx;
		color: #333333;
		line-height: 60rpx;
	}
</style>
