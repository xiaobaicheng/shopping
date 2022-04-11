<template>
	<view>
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
		name:"ShopList",
		data() {
			return {
				
			}
		},
		methods: {
			
		}
	}
</script>

<style lang="less" scoped>
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

			&:hover {
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
				height: 380rpx;
				margin-bottom: 30rpx;
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
