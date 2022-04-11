<template>
	<view class="">

		<view class="content">
			<swiper :indicator-dots="true" :autoplay="true" :interval="3000" :duration="1000">
				<swiper-item v-for="item in swiper" :key="item.goods_id">
					<image :src="item.image_src" mode="widthFix"></image>
				</swiper-item>
			</swiper>
		</view>
		<view class="naw"  >
			<view class="view-one" v-for="(item,index) in naw" :key="index">
				<view :class="item.icon" @click="path(item.path)"></view>
				<text>{{item.title}}</text>
			</view>
		</view>
		<!-- 推荐商品 -->
		<view class="recommend">
			推荐商品
		</view>
		<ShopList></ShopList>
	</view>
</template>

<script>
	import ShopList from "../../component/ShopList/ShopList"
 	export default {
		name:"index",
		components:{ShopList},
		data() {
			return {
				title: 'Hello',																											
				swiper: [],
				arr: [],
				newArr: [],
				sasa: '',
				naw:[
					{
						icon:"iconfont icon-ziyuan",
						title:"商城",
						path:"/pages/shop/shop"
					},
					{
						icon:"iconfont icon-guanyuwomen",
						title:"联系我们",
						path:"/pages/shop/Contactus"
					},
					{
						icon:"iconfont icon-tupian",
						title:"社区图片",
						path:"/pages/shop/community"
					},
					{
						icon:"iconfont icon-shipin",
						title:"学习视频",
						path:"/pages/shop/video"
					}
				]
			}
		},
		onLoad() {
			this.getSwiper()
			this.getremmend()
			this.getdada()
		},
		methods: {
			path(url){
				uni.navigateTo({
					url
				})
			},
			//获取推荐商品
			async getremmend() {
				let res = await this.$myRuquest({
					url: "/goods/detail",
				})
				// console.log(res);
			},
			getdada() {
				uni.request({
					url: 'http://api-hmugo-web.itheima.net/api/public/v1/home/floordata',
					method: 'GET',
					data: {},
					success: res => {
						// console.log(res);
					},
					fail: (error) => {
						console.log(error);
					},
				});
			},
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
		},
	
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

	
</style>
