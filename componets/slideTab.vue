<template>
	<view class="wrapper">
		
		<view class="tabli" :class="index==nums?'active':''" v-for="(item,index) in list" @click="tabCli(index)">
			{{item.title}}
		</view>

	</view>
</template>

<script>
	export default{
		methods:{
			tabCli(index){
				let sortid = this.list[index].num;
				console.log(sortid);
				this.$emit('sortid',sortid);
				this.nums=index
			}
		},
		data(){
			return{
				nums:0,
				list:[
					{title:'热榜',num:'0'},
					{title:'品牌',num:'104'},
					{title:'财经',num:'105'},
					{title:'军事',num:'109'},
					{title:'教育',num:'113'},
				]
			}
		}
	}
</script>

<style scoped lang="less">
	.wrapper{
		width: 90%;
		overflow-x: auto;
		font-size: 35rpx;
		padding: 30rpx 25rpx;
		display: flex;
		align-items: flex-end;
		.tabli{
			margin: 0 30rpx;
			width: 80rpx;
			flex-shrink: 0;
		}
	}
	.active{
		border-bottom: #706967 solid 2rpx;
		padding-bottom: 10rpx;
		font-weight: 800;
		font-size: 40rpx;
	}
	
</style>
