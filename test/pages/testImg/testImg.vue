<template>
	<view class="test-img">
		<button type="primary" @click="clickHandle">上传图片</button>
		<image v-for="(item,i) in imgArr" :src="item" :key="i" mode="aspectFit" @click="imgClick(item)"></image>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				imgArr: []
			}
		},
		methods: {
			/**
			 * 上传图片
			 */
			clickHandle() {
				uni.chooseImage({
					count: 5,
					success: (res) => {
						console.log(res)
						this.imgArr = res.tempFilePaths
					}
				})
			},
			imgClick(item) {
				uni.previewImage({
					current: item,
					urls: this.imgArr
				})
			}
		}
	}
</script>

<style>
	.test-img {
	}
</style>
