<template>
	<view >
		<view class="content">
			{{msg}}
		</view>
		<view>{{flag?'三元运算符成功':'三元运算符失败'}}</view>
		<view style="margin: 20px 0;"></view>
		<button type="primary" size="mini" @click="clickHandle">点击事件测试</button>
		<button type="default" @click="pullDown">点击刷新</button>
		<view >v-for练习</view>
		<view v-for="(item,i) in arr" :key='i' class="item">
			序号：{{i+1}} &nbsp;&nbsp;  名字：{{item.name}} &nbsp;&nbsp; 年龄：{{item.age}}
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				msg: 'hellow word',
				flag: true,
				arr: [
					{
						name: '王大',
						age: 18,
					},
					{
						name: '张三',
						age: 19,
					},
					{
						name: '李四',
						age: 20,
					},
				]
			}
		},
		onPullDownRefresh() {
			console.log('触发了下拉刷新')
			setTimeout(() =>{
				this.arr = [
					{
						name: 'cs1',
						age: 20
					},
					{
						name: '张三丰',
						age: 60
					},
					{
						name: 'xxs',
						age: 30
					},
				]
				uni.stopPullDownRefresh()
			},1000) 
			
		},
		onReachBottom() {
			console.log('触底了')
			this.arr = [...this.arr,...[{
						name: 'cs4',
						age: 22
					},
					{
						name: 'cs5',
						age: 50
					},
					{
						name: 'cs6',
						age: 43
					}]]
		},
		methods:{
			clickHandle(e) {
				console.log('事件点击成功',e)
			},
			pullDown() {
				uni.startPullDownRefresh()
			}
		}
	}
</script>

<style>
	.item {
		height: 300px;
		line-height: 300px;
	}
</style>
