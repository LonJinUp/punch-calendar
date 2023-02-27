<template>
	<view class="content">
		<punch-calendar @chooseDay="chooseDay" :errorList="errorList" :successList="successList" ref="calendar"></punch-calendar>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				successList: ['1676995200000'],
				errorList: ['1676908800000'],
			}
		},
		onLoad() {
			this.$refs.calendar.initCalendar()
		},
		methods: {
			chooseDay(val) {
				console.log(val)
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
