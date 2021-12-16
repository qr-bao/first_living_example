<template>
	<view class="wrapper">

		<view class="li" v-for="(item,index) in sendnews" @click="gotopage(index)">
			<view class="num">
				{{index<=2?index+1:''}}
			</view>
			<view class="title">
				{{item.title}}
			</view>
			<view class="text">
				{{item.digest}}
			</view>
		</view>
	</view>
	
</template>

<script>
	export default{
		props:{
			sendnews:{
				require:true
			}
		},
		data(){
			return{
				lists:[
					{
						title:'新闻1',
						text:'新闻内容写在这儿长度测试hi欧萨皇帝搜狐地搜啊都会死哦都会死哦爱德华死哦的阿斯哦哦奥的斯哦啊好赛欧iodsaio艾斯欧大奖赛殴打决赛的决赛殴打睡觉哎迪赛噢对就'
					},
					{
						title:'新闻2',
						text:'新闻内容写在这儿长度测试hi欧萨皇帝搜狐地搜啊都会死哦都会死哦爱德华死哦的阿斯哦哦奥的斯哦啊好赛欧iodsaio艾斯欧大奖赛殴打决赛的决赛殴打睡觉哎迪赛噢对就'
					},
					{
						title:'新闻3',
						text:'新闻内容写在这儿长度测试hi欧萨皇帝搜狐地搜啊都会死哦都会死哦爱德华死哦的阿斯哦哦奥的斯哦啊好赛欧iodsaio艾斯欧大奖赛殴打决赛的决赛殴打睡觉哎迪赛噢对就'
					},
				]			
			}
		},
		methods:{
			gotopage(val){
				let id = this.sendnews[val].article_id;
				let title = this.sendnews[val].title;
				console.log(id,title);
				uni.setStorageSync('id',id);
				uni.setStorageSync('title',title);
				uni.navigateTo({
					url:"../../pages/newsDetails/newsDetails"
				})
			}
		},
	}
</script>

<style scoped lang="less">
	.wrapper{

	}
	.li{
		border:3rpx solid #abaaaa;
		border-top: none;
		border-bottom-right-radius: 25px;
		border-bottom-left-radius: 25px;
		box-shadow: 2px 10px 25px -16px rgba(0,0,0,0.75);
		min-height: 210rpx;
		padding: 30rpx 40rpx 20rpx 80rpx;
		.title{
			font-weight: 600;
			line-height: 60rpx;
			font-size: 40rpx;
		}
		.text{
			font-size: 34rpx;
			color: #333333;
			line-height: 60rpx;
			overflow : hidden;
			text-overflow: ellipsis;
			display: -webkit-box;
			-webkit-line-clamp: 4;
			-webkit-box-orient: vertical;
		}
		.num{
			position: absolute;
			left: 40rpx;
			font-size: 30rpx;
			text-align: center;
			width: 35rpx;
			background-size: 100% 100%;
		}

	}
	.li:nth-of-type(1){
		.num{
			background-image: url('../../static/list1.png');
		}
	}
	.li:nth-of-type(2){
		.num{
			background-image: url('../../static/list2.png');
		}
	}
	.li:nth-of-type(3){
		.num{
			background-image: url('../../static/list3.png');
		}
	}
</style>
