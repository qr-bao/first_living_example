
<template>
    <view class="lianggekuang">
		<textarea readonly placeholder="请输入关键字" class="shurukuang" @click="toeditor1" v-model="kw"></textarea>
		<!-- <view class="wangyouyidian"> -->
		
		
		<button @click="getData()" class="anniu">确定</button>
		<!-- </view> -->
		<textarea readonly placeholder="生成的文章" class="shurukuang-xiamian" @click="toeditor2" v-model="context"></textarea>
		
		
    </view>
</template>
 
<script>
	
	var _self;
    export default {
        data() {
            return {
				kw: '',
				context: ''
            }
        },
        onLoad(data){
			_self = this;
			uni.setStorage({
			    key: 'kw',
			    data: this.kw,
			    success: function () {
			        console.log('success');
			    }
			});
			uni.setStorage({
			    key: 'context',
			    data: this.context,
			    success: function () {
			        console.log('success');
			    }
			});
        },

		onShow() {
			console.log('!!!!!!')
			uni.getStorage({
			    key: 'kw',
			    success: function (res) {
			        _self.kw = res.data
			    }
			});
			uni.getStorage({
			    key: 'context',
			    success: function (res) {
			        _self.context = res.data
			    }
			});
		},
		
        methods: {
            //跳转到子页面
            toeditor1(){
                uni.navigateTo({ url: '/pages/editor/editor?flag=1'});
            },
			toeditor2(){
			    uni.navigateTo({ url: '/pages/editor/editor?flag=2'});
				uni.setStorage({
				    key: 'context',
				    data: this.context,
				    success: function () {
				        console.log('success');
				    }
				});
			},
			getData: function() {
				// var api = 'http://127.0.0.1:8000/test';
				var api = 'http://122.9.13.250:8001/test';
				console.log(this.kw);
				uni.request({
				    url: api,
				    data: {
				        'kw': this.kw.replace("\n", '')
				    },
					method: 'POST',
					header: {
					    'content-type': 'application/x-www-form-urlencoded'
					},
				    success: (res) => {
				        console.log(res.data);
				        this.text = 'request success';
						this.context = res.data['1'];
						uni.setStorage({
						    key: 'context',
						    data: res.data['1'],
						    success: function () {
						        console.log('success');
						    }
						});
				    }
				});
			}
        }
    }
</script>
 
<style scoped>
	.shurukuang {
		top: 20px;
		/* left: 20rpx; */
		height: 200rpx;
		width: 90%;
		border: 1px solid #ccc;
		border-radius: 10px;
		padding-top: 10rpx;
		padding-left: 15px;
		word-wrap : break-word;
		margin-bottom: 80rpx;
		}
	.shurukuang-xiamian {
		/* left: 20rpx; */
		/* height: auto; */
		width: 90%;
		border: 1px solid #ccc;
		border-radius: 10px;
		padding: 10px 10px 0;
		/* word-wrap : break-word; */
		margin-top: 38rpx;
		}
	.lianggekuang {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		/* height: 100vh; */
		width: 100%;
	}
	.anniu{
		font-size: 16px;
		color: #fff;
		height: 40px;
		width: 90%;
		border: 1px solid #22C704;
		border-radius: 10px;
		line-height: 39px;
		background-color: #22C704;
	}
	.wangyouyidian{
		/* padding-top: 10%; */
		/* padding-left:540rpx; */
	}
</style>
