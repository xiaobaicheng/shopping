<template>
	<view>
		<ShopList></ShopList>
	</view>
</template>

<script>
	import ShopList from "../../component/ShopList/ShopList"
	export default {
		name:"shop",
		components:{ShopList},
		
		data() {
			return {
				dad:[]
			}
		},
		methods: {
		async	getshoplist(){
				uni.request({
					url:"http://api-hmugo-web.itheima.net/api/public/v1/home/floordata",
					method:"GET",
					data:{},
					
					 success: res => {
						this.dad = res.data.message
						console.log(this.dad);
					},
					fail: (error) => {
						console.log(error);
					},
				})
				
			}
		},
		onLoad(){
			this.getshoplist()
		}
	}
</script>

<style>

</style>
