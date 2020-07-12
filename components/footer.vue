<template name='footer'>
	<view class='footer'>
		<view v-for="(item,index) in menuList" :key="index">
			<navigator :url="item.url" hover-class="navigator-hover">
				<view>
					<i class="iconfont">{{item.icon}}</i>
					<view class="">
						{{item.name}}
					</view>
				</view>
			</navigator>
		</view>
	</view>
</template>

<script>
	export default {
		name: 'footer',
		data() {
			return {
				menuList: [{
						name: '首页',
						icon: '\ue629',
						url: '/pages/index/index'
					},
					{
						name: '记录',
						icon: '\ue66b',
						url: '/pages/record/record'
					},
					{
						name: '分享',
						icon: '\ue60e',
						url: '/pages/share/share'
					},
					{
						name: '好货',
						icon: '\ue602',
						url: '/pages/goods/goods'
					},
					{
						name: '我的',
						icon: '\ue629',
						url: '/pages/personal/personal'
					},
				]
			};
		}
	}
</script>

<style lang="scss">
	.footer {
		position: fixed;
		bottom: 0;
		left: 0;
		width: 100%;
		height: 15vw;
		display: flex;
		flex-direction: row;
		justify-content: center;
		align-items: center;
		border-top: 1px solid #c3c3c3;

		>view {
			flex: 1;
			// height: 10vw;
			font-size: 10px;
			text-align: center;

			.iconfont {
				margin-bottom: 2px;
			}
		}
	}
</style>
