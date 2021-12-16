<template>
	<view class="wrapper">
		<image src="../static/search.png" mode="" @click="gotopage"></image>
		<input type="text" value="" placeholder="搜索内容" @input="changecontent"/>
	</view>
</template>

<script>
	export default {
		data(){
			return{
				content:'',
			}
		},
		methods:{
			changecontent(e){
				console.log(e.detail.value);
				let content = e.detail.value;
				this.content = content;
			},
			gotopage(){
				uni.setStorageSync('searchcontent',this.content);
				this.$emit('sendcontent',true)
			}
		}
	}
</script>

<style scoped lang="less">
	.wrapper{
		
		border:2px solid #cdcdcd;
		width: 98%;
		height: 60rpx;
		font-size: 35rpx;
		border-radius: 50rpx;
		display: flex;
		align-items: center;
		position: relative;
		image{
			margin: 0 25rpx;
			width: 40rpx;
			height: 40rpx;
			position: absolute;
			right: 0;
		}
		input{
			
			padding: 0  15rpx;
			box-sizing: border-box;
		}
	}
</style>
