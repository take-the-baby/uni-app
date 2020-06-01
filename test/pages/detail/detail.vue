<template>
	<view>
		<view >
			<text>文本测试</text>
		</view>
		<view >
			<text selectable>文本测试(selectable)是否可选</text>
		</view>
		<view >
			<text space="emsp">文本  测试space--emsp,一个中文字符空格大小</text>
		</view>
		<view >
			<text space="ensp">文本  测试space--ensp,半个中文字符空格大小</text>
		</view>
		<view >
			<text space="nbsp" style="font-size: 20px;">文本  测试space--nbsp,根据字体设置的空格大小</text>
		</view>
		<view >
			<text >&amp;现版本默认支持decode</text>
		</view>
		<view class="view-class1" hover-class="box-active">
			view标签hover-class测试
		</view>
		<view class="view-box" hover-class="view-boxActive" hover-start-time="1000" hover-stay-time="1000">
			<view class="view-class2" hover-class="box2-active" hover-stop-propagation>
				view标签hover-stop-propagation测试
			</view>
		</view>
		<button type="default" class="button">按钮(默认)</button>
		<button type="primary" size="mini">按钮(小)</button>
		<button type="default" plain>按钮(镂空)</button>
		<button type="default" disabled>按钮(禁用)</button>
		<button type="default" loading>按钮(loading)</button>
		<view>--------------------------</view>
		<image src="http://img.mp.itc.cn/upload/20170401/2a003704efe043aca36b9e9c2d8cb48e.gif" mode=""></image>
		<image src="http://img.mp.itc.cn/upload/20170401/2a003704efe043aca36b9e9c2d8cb48e.gif" mode="aspectFill"></image>
		<image src="http://img.mp.itc.cn/upload/20170401/2a003704efe043aca36b9e9c2d8cb48e.gif" mode="aspectFit"></image>
		
	</view>
</template>

<script>
	export default {
		onLoad(option) {
			console.log(option)
		}
	}
	
</script>

<style>
	.view-class1 {
		width: 100%;
		height: 30px;
		color: #555555;
		margin-top: 1rem;
		padding: 20px;
		border-top: 1rpx solid #007AFF;
	}
	.view-class2 {
		width: 80%;
		height: 30px;
		color: #555555;
		font-size: 14px;
		background-color: #EEEEEE;
	}
	.box2-active {
		width: 80%;
		height: 30px;
		background-color: #333333;
	}
	.box-active {
		width: 100%;
		height: 80px;
		color: #007AFF;
	}
	.view-box {
		width: 100%;
		height: 60px;
		background-color: #4CD964;
	}
	.view-boxActive {
		width: 100%;
		height: 60px;
		background-color: #F0AD4E;
	}
	.button {
		margin-top: 1rem;
	}
</style>
