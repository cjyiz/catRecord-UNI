<template>
	<view>
		<view class="per-header">
			<view class="per-name">
				<image src="../../static/logo.png" mode=""></image>
				<span>昵称</span>
				<span>s</span>
			</view>
			<view class="per-card">
				<view class="">
					优惠券
				</view>
				<view class="">
					猫咪卡
				</view>
				<view class="">
					积分
				</view>
			</view>
		</view>
		
		<view class="">
			<view class="">
				我的预约
			</view>
			<view class="">
				我的订单
			</view>
		</view>
	<Footer></Footer>
	</view>
</template>

<script>
	import Footer from '@/components/footer.vue'
	export default {
		data() {
			return {

			};
		},
		components:{
			Footer
		}
	}
</script>

<style lang="scss">

</style>
