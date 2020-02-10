<template>
	<view>
		<view class="nav">
			<view class="navTop">
				<view class="navbar">
					<view v-for="(item, index) in navList" :key="index" class="nav-item" :class="{ current: tabCurrentIndex === index }"
					 @click="tabClick(index)">
						{{ item.text }}
					</view>
				</view>
				<view class='navTo'>

					<view></view>
				</view>
			</view>

			<!-- 显示头像 -->
			<view class="list" v-for="(item, index) in navList" :key="index" v-if="tabCurrentIndex === index">
				<view class="catAvatar">
					cjyiz+{{ item.state }}
				</view>
				<view class='catCondition'>
					<view>距离上次洗澡第{{ item.state }}天</view>
					<view>距离上次驱虫第{{ item.state }}天</view>
					<view>距离上次疫苗第{{ item.state }}天</view>
				</view>
			</view>
		</view>

		<view class='options'>
			<view class="optionName">
				<view v-for="(item,index) in optionList" :class="{optionCurrent:tabCurrentIndex2===index}" :key="index" @click="tabClick2(index)">
					{{item.name}}
				</view>
			</view>
			<view class="">
				<view v-if='tabCurrentIndex2===0'>
					<BOOK></BOOK>
				</view>
				<view v-if='tabCurrentIndex2===1'>
					<ORDER></ORDER>
				</view>
				<view v-if='tabCurrentIndex2===2'>
					<MEMBERCARD></MEMBERCARD>
				</view>
			</view>
		</view>

	
	    <view class="footer">
			<view v-for="(item,index) in menuList" :key="index">
				<!-- <image :src="item.img" mode=""></image> -->
				<view>
				<i class="iconfont">{{item.icon}}</i>
				{{item.name}}
				</view>
				
			</view>
	    </view>
	</view>
</template>

<script>
	import BOOK from '@/components/book.vue'
	import ORDER from '@/components/order.vue'
	import MEMBERCARD from '@/components/memberCard.vue'
	import IconSvg from '@/components/icon.vue'
	export default {
		data() {
			return {
				tabCurrentIndex: 0,
				tabCurrentIndex2: 1,
				navList: [{
						state: 0,
						text: '全部',
						orderList: []
					},
					{
						state: 1,
						text: '西西',
						orderList: []
					},
					{
						state: 2,
						text: '花花',
						orderList: []
					},
					{
						state: 3,
						text: '兰兰',
						orderList: []
					},
					{
						state: 4,
						text: '妙妙',
						orderList: []
					}
				],
				optionList: [{
						name: '预约',
						state: '1'
					},
					{
						name: '订单',
						state: '1'
					},
					{
						name: '会员卡',
						state: '1'
					}
				],
			menuList:[
				{
					name:'首页',
					icon:'\ue629'
				},
				{
					name:'记录',
					icon:'\ue66b'
				},
				{
					name:'分享',
					icon:'\ue60e'
				},
				{
					name:'好货',
					icon:'\ue602'
				},
				{
					name:'我的',
					icon:'\ue629'
				},
			]
			}
		},
		components: {
			BOOK,
			ORDER,
		    MEMBERCARD,
			IconSvg
		},
		onLoad(optioons) {
			this.tabCurrentIndex = 0
		},
		methods: {
			changeTab(e) {
				this.tabCurrentIndex = e.target.current;
			},
			//顶部tab点击
			tabClick(index) {
				this.tabCurrentIndex = index;
			},

			tabClick2(index) {
				this.tabCurrentIndex2 = index;
				console.log(this.tabCurrentIndex2)
			}
		}
	}
</script>

<style lang='scss'>
	.nav {
		background-color: #C5F3FF;

		.navTop {
			display: flex;
			flex-direction: row;

			.navbar {
				display: flex;
				width: 65%;
				height: 40px;
				padding: 0 5px;
				position: relative;
				z-index: 10;

				.nav-item {
					flex: 1;
					display: flex;
					justify-content: center;
					align-items: center;
					height: 100%;
					font-size: 15px;
					color: #fff;
					position: relative;

					&.current {
						background-color: #797979;
						border-radius: 30rpx;
						/* 下面是tab标签下划线 */
						/* 	&:after {
						content: '';
						position: absolute;
						left: 50%;
						bottom: 0;
						transform: translateX(-50%);
						width: 44px;
						height: 0;
						border-bottom: 2px solid red;
					} */
					}
				}
			}

			.navTo {
				width: 35%;
				display: flex;
				flex-direction: column;
				align-items: center;
				justify-content: center;

				>view {
					height: 80rpx;
					width: 70rpx;
					background-color: red;
				}
			}
		}

		.list {
			width: 100%;

			.catAvatar::after {
				content: "";
				display: block;
				height: 1rpx;
				width: 90%;
				background-color: grey;
				margin: 10rpx 5%;
			}

			.catCondition {
				display: flex;
				flex-direction: row;
				justify-content: center;
				align-items: center;
				width: 100%;

				>view {
					height: 220rpx;
					width: 220rpx;
					font-size: 20rpx;
					text-align: center;
					border: 5rpx solid #FFCC33;
					border-radius: 220rpx;
				}

				>view:nth-child(2) {
					margin: 0 20rpx;
				}
			}
		}


	}



	.options {
		.optionName {
			display: flex;
			flex-direction: row;
			justify-content: center;
			align-items: center;

			>view {
				flex: 1;
				text-align: center;
				;
			}

			.optionCurrent {
				;
				border-bottom: 2px solid red;
			}

		}
	}

    .footer{
		display: flex;
		flex-direction: row;
		justify-content: center;
		align-items: center;
		border: 1px solid red;
		>view{
			flex: 1;
			height: 40rpx;
			
		}
	}
</style>
