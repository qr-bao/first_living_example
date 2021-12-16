<template>
	<view>
		<view class="search">
			<Search></Search>
		</view>
		<view class="content">
			<view v-for="(item,index) in messagelist" :key="index">
				<Messageli :sendmessage='item'></Messageli>
			</view>
		</view>
	</view>
</template>

<script>
	import Search from '../../componets/search.vue';
	import Messageli from '../../componets/messageli.vue';
	export default {
		components: {
			Search,
			Messageli,
		},
		onLoad() {
			let content = uni.getStorageSync('searchcontent');
		},
		data() {
			return {
				messagelist: [{
					title: '这是标题',
					content: "这是新闻简介这是介这是新闻简介这是新闻简介这是新闻简介这是新闻简介这是新闻简介这是新闻简介"
				}, {
					title: '这是标题',
					content: "新闻简介这是新闻简介新闻简介这是新闻简介这是新闻简介这是新闻简介这是新闻简介这是新闻简介"
				},  {
					title: '这是标题',
					content: "闻简介这新闻简介这是新闻简介这是新闻简介这是新闻简介这是新闻简介这是新闻简介这是新闻简介这是新闻简介这是新闻简介这是新闻简介"
				}]
			}
		},
		methods: {

		}
	}
</script>

<style scoped lang="less">
	.search {
		padding: 30rpx 0;
		box-sizing: border-box;
		box-shadow: 0px 3px 6px rgba(0, 0, 0, 0.16);
	}
</style>
