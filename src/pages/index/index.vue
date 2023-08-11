<template>
	<view class="content">
		<!-- <web-view
            src="https://m-mall.svw-volkswagen.com/marketing/activity/1684091248959012866?processKey=MF90189799&nodeKey=N1690353629211&utm_term=mp6-13-1"
    
        ></web-view> -->
		<image src="https://brand2.svw-volkswagen.com/cms/prod/I/20230804/f09554dd2d5b39f04636dd31b782aab3.jpg"></image>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello'
			}
		},
		onLoad() {

		},
		onShareAppMessage() {
			
		},
		methods: {
			
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

	.logo {
		height: 200rpx;
		width: 200rpx;
		margin: 200rpx auto 50rpx auto;
	}

	.text-area {
		display: flex;
		justify-content: center;
	}

	.title {
		font-size: 36rpx;
		color: #8f8f94;
	}
</style>
