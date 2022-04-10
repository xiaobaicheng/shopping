<template>
	<view class="">

		<view class="content">
			<swiper :indicator-dots="true" :autoplay="true" :interval="3000" :duration="1000">
				<swiper-item v-for="item in swiper" :key="item.goods_id">
					<image :src="item.image_src" mode="widthFix"></image>
				</swiper-item>
			</swiper>
		</view>
		<view class="naw">
			<view class="view-one">
				<view class="iconfont icon-ziyuan"></view>
				<text>商城</text>
			</view>
			<view class="view-one">
				<view class="iconfont icon-guanyuwomen"></view>
				<text>联系我们</text>
			</view>
			<view class="view-one">
				<view class="iconfont icon-tupian"></view>
				<text>社区图片</text>
			</view>
			<view class="view-one">
				<view class="iconfont icon-shipin"></view>
				<text>学习视频</text>
			</view>
		</view>
		<!-- 推荐商品 -->
		<view class="recommend">
			推荐商品
		</view>
		<view class="recommend-box">
			<view class="one-box">
				<view class="img-box">
					<image
						src="//cdn.cnbj1.fds.api.mi-img.com/mi-mall/d764150a470174741d8b0b04515f7a78.jpg?thumb=1&w=350&h=350&f=webp&q=90"
						mode=""></image>
				</view>
				<view class="phonename">
					<text>Redmi 10A</text>
					<text class="desc">大电池，大音量，大屏幕</text>
				</view>
				<view class="picre">
					<text class="picre-one">649元起</text>
					<text class="del">699元</text>
				</view>
			</view>
			<view class="one-box">
				<view class="img-box">
					<image
						src="//cdn.cnbj1.fds.api.mi-img.com/mi-mall/d764150a470174741d8b0b04515f7a78.jpg?thumb=1&w=350&h=350&f=webp&q=90"
						mode=""></image>
				</view>
				<view class="phonename">
					<text>Redmi 10A</text>
					<text class="desc">大电池，大音量，大屏幕</text>
				</view>
				<view class="picre">
					<text class="picre-one">649元起</text>
					<text class="del">699元</text>
				</view>
			</view>
			<view class="one-box">
				<view class="img-box">
					<image
						src="//cdn.cnbj1.fds.api.mi-img.com/mi-mall/d764150a470174741d8b0b04515f7a78.jpg?thumb=1&w=350&h=350&f=webp&q=90"
						mode=""></image>
				</view>
				<view class="phonename">
					<text>Redmi 10A</text>
					<text class="desc">大电池，大音量，大屏幕</text>
				</view>
				<view class="picre">
					<text class="picre-one">649元起</text>
					<text class="del">699元</text>
				</view>
			</view>
			<view class="one-box">
				<view class="img-box">
					<image
						src="//cdn.cnbj1.fds.api.mi-img.com/mi-mall/d764150a470174741d8b0b04515f7a78.jpg?thumb=1&w=350&h=350&f=webp&q=90"
						mode=""></image>
				</view>
				<view class="phonename">
					<text>Redmi 10A</text>
					<text class="desc">大电池，大音量，大屏幕</text>
				</view>
				<view class="picre">
					<text class="picre-one">649元起</text>
					<text class="del">699元</text>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello',
				swiper: [],
				arr: [],
				newArr: [],
				sasa: ''
			}
		},
		onLoad() {
			this.getSwiper()
		},
		methods: {
			async getSwiper() {
				const res = await this.$myRuquest({
					url: "/home/swiperdata"
				})
				this.swiper = res.data.message
				this.swiper.forEach((item, index) => {
					this.arr = item.image_src.split("");
					this.newArr = this.arr.splice(4, 1)
					this.sasa = this.arr.join("")
					item.image_src = this.sasa
				})
			}
		}
	}
</script>
<style lang="less" scoped>
	.content {
		height: 400rpx;
		width: 98%;
		margin: auto;

		swiper {
			width: 100%;
			border-radius: 14rpx;

			image {
				width: 100%;
			}
		}
	}

	.naw {
		display: flex;
		margin-top: -40rpx;

		.view-one {
			text-align: center;
			width: 25%;

			.iconfont {
				height: 120rpx;
				width: 120rpx;
				margin-left: 30rpx;
				border-radius: 50%;
				background-color: #DD524D;
				font-size: 70rpx;
				line-height: 120rpx;
			}
		}
	}

	.recommend {
		width: 100%;
		height: 100rpx;
		background-color: #808080;
		text-align: center;
		line-height: 100rpx;
		font-size: 40rpx;
		letter-spacing: 10rpx;
	}

	.recommend-box {
		margin-top: 40rpx;
		width: 90%;
		margin-left: 5%;
		margin-right: 5%;
		display: flex;
		flex-wrap: wrap;
		justify-content: space-between;

		.one-box {
			transition: all .2s linear;
			width: 48%;
			text-align: center;
			margin-top: 20rpx;
			box-shadow: 0 0 8px #808080;
			overflow: hidden;
			&:hover{
				transform: translateY(-10px);
				transition: 2s;
			}

			.picre {
				.picre-one {
					color: #ff6700;
				}

				.del {
					margin-left: .5em;
					color: #b0b0b0;
				}
			}

			.phonename {
				margin-top: -20rpx;
				display: flex;
				flex-direction: column;
				font-size: 14px;
				font-weight: 400;
				color: #333;

				.desc {
					font-size: 12px;
					color: #b0b0b0;
				}
			}

			.img-box {
				height: 480rpx;
				width: 280rpx;
				margin-left: 10%;

				image {
					height: 100%;
					width: 100%;
				}
			}
		}
	}
</style>
