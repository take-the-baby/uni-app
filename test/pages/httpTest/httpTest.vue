<template>
	<view >
		<button @click="clickHandle">发送请求</button>
		<button type="primary" @click="clickSetData">数据缓存</button>
		<button type="primary" @click="clickgetData">得到缓存数据</button>
		<button type="primary" @click="clickDeletData">得到缓存数据</button>
		<!-- #ifdef H5 -->
		<view >这段文字只在H5中可见</view>
		<!-- #endif -->
		<!-- #ifdef MP-WEIXIN -->
		<view class="">这段文字只能在小程序中可见</view>
		<!-- #endif -->
		<text class="text-test">不同终端不同样式测试</text>
		<view class="">
			navigator跳转
		</view>
		<navigator url="../detail/detail" >跳转至详情页</navigator>
		<navigator url="../index/index" open-type="switchTab">跳转至首页(tabBar)</navigator>
		<view class="">
			javeScript方式跳转
		</view>
		<button type="primary" @click="gotoDedail">跳转至详情页</button>
		<button type="primary" @click="gotoIndex">跳转至首页</button>
		
	</view>
</template>

<script>
	export default {
		data() {
			return {
			
			}
		},
		onUnload() {
			console.log('页面被卸载了')
		},
		destroyed() {
			console.log('Vue实例被销毁了')
		},
		onLoad() {
			// #ifdef H5
			console.log('这段文字只在H5中展示！')
			// #endif
			// #ifdef MP-WEIXIN
			console.log('这段文字只在微信小程序中展示！')
			// #endif
		},
		onPullDownRefresh() {
			
			
		},
		onReachBottom() {
			
		},
		methods:{
			clickHandle(e) {
				uni.request({
					url: 'http://img.mp.itc.cn/upload/20170401/2a003704efe043aca36b9e9c2d8cb48e.gif',
					header: {
						'header-test': 'success'
					},
					method:"GET",
					success:(res)=> {
						console.log('接口返回成功')
					}
				})
			},
			clickSetData() {
				uni.setStorageSync('id',1)
				uni.setStorage({
					key: 'age',
					data: 11,
					success:(res) =>{
						console.log('缓存成功')
					}
				})
			},
			clickgetData() {
				uni.getStorage({
					key: 'age',
					success:(res)=> {
						console.log(res)
					}
				})
				let res = uni.getStorageSync('id');
				console.log(res)
			},
			clickDeletData() {
				uni.removeStorage({
					key: 'id',
					success:(res) =>{
						console.log(res)
					}
				})
				uni.removeStorageSync('age');
			},
			gotoDedail() {
				uni.navigateTo({
					url:'/pages/detail/detail?id=1&age=19',
					success:() =>{
						console.log('跳转详情页成功')
					}
				})
				
			},
			gotoIndex() {
				uni.switchTab({
					url:'/pages/index/index?id=1&age=19',
					success: () => {
						console.log('跳转至首页')
					}
				})
			}
		}
	}
</script>

<style>
	.item {
		height: 300px;
		line-height: 300px;
	}
	/* #ifdef H5*/
	.text-test {
		color: #007AFF;
		
	}
	/* #endif */
	/* #ifdef MP-WEIXIN*/
	.text-test {
		color: #DD524D
	}
	/* #endif */
</style>
