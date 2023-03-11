<template>
	<view class="content">
		<punch-calendar @chooseDay="chooseDay" :errorList="errorList" :successList="successList" ref="calendar"></punch-calendar>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				successList: ['1676995200000',],
				errorList: ['1676908800000'],
				
			}
		},
		onLoad() {
			this.$refs.calendar.initCalendar()
			
			// 模拟异步赋值
			let timer = setTimeout(()=>{
				this.addTimer()
			},2000)
		},
		methods: {
			chooseDay(val) {
				console.log(val)
			},
			
			addTimer() {
				this.successList = [...this.successList, '1678204800000']
			}
		}
	}
</script>

<style lang="scss">
	page{
		width: 100%;
		height: 100%;
	}
	.content {
		width: 100%;
		height: 100%;
		background: #f8f8f9;
		padding: 40rpx 32rpx;
	}
</style>
