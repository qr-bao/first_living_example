<template>
	<view class="content">
		<!-- 搜索 -->
		<view class="search">
			<Search v-on:sendcontent='getcontent'></Search>
		</view>
		<!-- 新闻部分 -->
		<view class="news">
			<!-- 头部 -->
			<view class="head">
				<image src="../../static/searchhead.png" mode=""></image>
			</view>
			<!-- 新闻列表 -->
			<view class="newlist">
				<view class="li" v-for="(item,index) in list" :key="index">
					<Searchli :sendinfo=list[index]></Searchli>
				</view>
			</view>
		</view>

	</view>
</template>

<script>
	import Search from '../../componets/search.vue'
	import Searchli from '../../componets/searchli.vue'
	
	export default {
		components: {
			Search,
			Searchli,
		},
		data() {
			return {
				list: [{
						url: "../static/1.png",
						content: '新闻标题1',
						index: 1
					},
					{
						url: "../static/2.png",
						content: '新闻标题1新闻标题1',
						index: 2
					},
					{
						url: "../static/3.png",
						content: '新闻标题1新闻标题1新闻标题1',
						index: 3
					},
					{
						url: "../static/4.png",
						content: '新闻标题1',
						index: 4
					},
					{
						url: "../static/5.png",
						content: '新闻标题1新闻标题1',
						index: 5
					},
					{
						url: "../static/6.png",
						content: '新闻标题1新闻标题1',
						index: 6
					},
					{
						url: "../static/7.png",
						content: '新闻标题1',
						index: 7
					},
					{
						url: "../static/8.png",
						content: '新闻标题1新闻标题1',
						index: 8
					},
				],
			}
		},
		onLoad() {
			uni.request({
				url: 'http://122.9.13.250:8000/get_news_digest',
				method: 'post',
				data: {
					sortid: '104',
					start: '0',
					end: '8',
				},
				header: {
					'Content-Type': 'application/x-www-form-urlencoded'
				},
				dataType: 'json',
				success: (val) => {
					console.log(val.data.news);
					let newslist = val.data.news;
					for (let i = 0; i < newslist.length; i++) {
						this.list[i].content = newslist[i].title;
					}
				}
			})
		},
		
		methods: {
			getcontent(val){
				let content = uni.getStorageSync('searchcontent');
				if( content==''){
					return;
				}
				uni.setStorageSync('id','6969215673109217800');
				uni.navigateTo({
					url:'../newsDetails/newsDetails'
				})
			}
		}
	}
	
</script>

<style lang="less" scoped>
	.search {
		margin-top: 40rpx;
		width: 90%;
		margin: 40rpx auto;
		box-sizing: border-box;
	}

	.news {
		width: 689rpx;
		margin: 40rpx auto;
		border: 2rpx solid #F3ECD8;
		border-radius: 20rpx;
		overflow: hidden;

		.head {
			width: 100%;
			height: 100rpx;
			margin-bottom: 20rpx;
			box-sizing: border-box;

			>image {
				width: 100%;
				height: 100%;
			}
		}

		.newlist {
			width: 100%;
			height: auto;

			.li {
				width: 100%;
				padding-left: 30rpx;
				padding-right: 30rpx;
				box-sizing: border-box;
				margin-bottom: 10rpx;
				font-size: 38rpx;
			}
		}
	}
</style>
