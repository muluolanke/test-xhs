<template>
	<view class="content">
		<view v-if="!location" @click="getLocation()">获取位置</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
        		location:false,
			}
		},
		onLoad() {

		},
		created(){
				this.locationInfo()
		},
		methods: {
			getLocation(){
				this.getLocationInfo()
			},
			// 自动定位
			getLocationInfo() {
				const that = this
				console.log("hh")
				uni.authorize({
					scope: 'scope.userLocation',
					success: () => {
						uni.getLocation({
							type: 'gcj02',
							geocode: true,
							success: (res) => {
								console.log(res)
							},
							fail: (res) => {
								console.log(res)
							}, 
						})
					},
					fail(res) {
						console.log(res)
					},
				})
			},
			locationInfo(){
				const that=this;
				uni.getSetting({
					success: (res) => {
						const userLocation = res.authSetting['scope.userLocation']
            if(userLocation){
              this.location=true;
            }
					}
				})
			},
		}
	}
</script>

<style>
	
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}

</style>

