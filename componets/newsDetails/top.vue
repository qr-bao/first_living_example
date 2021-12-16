<template>
	<view class="wrapper">
		<view class="search">
			<search></search>
		</view>
		
		<image src="../../static/loading.png" mode=""></image>
		<image src="../../static/1.jpg" mode=""></image>
	</view>
</template>

<script>
	import search from '../search.vue'
	export default{
		components:{
			search
		}
	}
</script>

<style scoped lang="less">
	
	.wrapper{
		padding: 15rpx 0;
		height: 80rpx;
		background-color: #e9f4fa;
		display: flex;
		align-items: center;
		image:nth-of-type(1){
			width: 30rpx;
			height: 30rpx;
			margin-left: 15rpx;
			margin-right: 40rpx;
		}
		image:nth-of-type(2){
			width: 80rpx;
			height: 80rpx;
			border-radius: 50%;
			
			
		}
		.search{
			margin-left: 40rpx;
			width: 532rpx;
		}

	}
</style>
