<template>
	<view :class="isvip ?'isvip':'' ">
		<top></top>
		<mid :sendcontext="context"></mid>
		<bottom v-if="isvip"  v-on:changevip="changevip"></bottom>
	</view>
</template>

<script>
	import top from '../../componets/newsDetails/top.vue'
	import mid from '../../componets/newsDetails/mid.vue'
	import bottom from '../../componets/newsDetails/bottom.vue'
	export default {
		components:{
			top,
			mid,
			bottom
		},
		onLoad() {
			let id = uni.getStorageSync('id');
			uni.request({
				url:'http://122.9.13.250:8000/get_news_by_id',
				method:'post',
				data:{
					sortid:'104',
					article_id:id,
				},
				header: {
				    'Content-Type': 'application/x-www-form-urlencoded'
				},
				dataType: 'json',
				success:(res)=>{
					// console.log(res.data.context);
					this.context = res.data.context;
				}
			})
		},
		data() {
			return {
				context:'',
				isvip:true,
			};
		},
		methods:{
			changevip(){
			console.log(222)
			this.isvip = !this.isvip;
			}
		}
	}
</script>

<style lang="less" scoped>
	.isvip{
		height: 100vh;
		overflow: hidden;
	}
</style>
