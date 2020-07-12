<template>
	<view>
		<uni-calendar class="calendar" :insert="true" :lunar="true" :start-date="'2019-3-2'" :end-date="'2019-5-20'" @change="change"></uni-calendar>
		<view class="">
			洗澡<switch checked @change="switch1Change" />
		</view>
		<view class="">
			体内驱虫<switch checked @change="switch2Change" />
		</view>
		<view class="">
			体外驱虫<switch checked @change="switch3Change" />
		</view>
		<view class="">
			疫苗<switch checked @change="switch4Change" />
		</view>
		<Footer></Footer>
	</view>
</template>

<script>
	import uniCalendar from '@/components/uni-calendar/uni-calendar.vue'
	import Footer from '@/components/footer.vue'
	export default {
		components: {
			uniCalendar,
			Footer
		},
		data() {
			return {};
		},
		methods: {
			change(e) {
				console.log(e);
			},
			switch1Change: function(e) {
				console.log('switch1 发生 change 事件，携带值为', e.target.value)
			},
			switch2Change: function(e) {
				console.log('switch2 发生 change 事件，携带值为', e.target.value)
			},
			switch3Change: function(e) {
				console.log('switch3 发生 change 事件，携带值为', e.target.value)
			},
			switch4Change: function(e) {
				console.log('switch4 发生 change 事件，携带值为', e.target.value)
			},
		}
	};
</script>

<style lang="scss">

</style>
