<template>
	<view>
			<button @click="back" class="anniu">确定</button>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				kw: ''
			}
		},
		onLoad(options) {
			this.kw = options.kw
		},
		methods: {
			back(){
				let pages = getCurrentPages();  //获取所有页面栈实例列表
				let nowPage = pages[ pages.length - 1];  //当前页页面实例
				let prevPage = pages[ pages.length - 2 ];  //上一页页面实例
				prevPage.$vm.kw = 'fgdfhfsvgbhn';   //修改上一页data里面的searchVal参数值为1211
				uni.navigateBack({  //uni.navigateTo跳转的返回，默认1为返回上一级
					delta: 1
				});
			}
		}
	}
</script>

<style>

</style>
