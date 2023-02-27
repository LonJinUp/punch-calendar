# punch-calendar

> [punch-calendar](https://github.com/LonJinUp/punch-calendar)为有打卡需求制作的日历，可标记小圆点。简单配置即可使用，代码体积小，无第三方引用。

## 使用方法

demo: 
```html
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
			// 初始化必须执行该函数
			this.$refs.calendar.initCalendar()
		},
		methods: {
			chooseDay(val) {
				console.log(val)
			}
		}
	}
</script>
```

### 配置说明：

参数说明：

| 参数        | 说明                         | 默认值 | 类型  |
| ----------- | ---------------------------- | ------ | ----- |
| successList | 打卡成功标记，传入13位时间戳 | []     | Array |
| errorList   | 打卡异常标记，传入13位时间戳 | []     | Array |


回调方法
| 方法名称   | 说明                 | 返回值                       |
| ---------- | -------------------- | ---------------------------- |
| @chooseDay | 点击某日时候执行函数 | 返回一个对象，包含年、月、日 |

