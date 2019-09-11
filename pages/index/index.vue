<template>
	<view class="content">
		<image class="logo" src="/static/photo.png"></image>
		<view class="text-area">
			<text class="title" @click="goToInfoList()">{{title}}</text>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: '点我查看新闻哦~'
			}
		},
		onLaunch: function() {
		    console.log('App Launch')
		},
		onShow: function() {
		    console.log('App Show')
		},
		onHide: function() {
		    console.log('App Hide')
		},
		onLoad() {
			console.log(this.$mp.page.route);
			
		},
		methods: {
			goToInfoList() {
				uni.navigateTo({
					url: '/pages/info/list?content=我是参数'
				})
			}
		}
	}
</script>

<style>
	.content {
		width: 100%;
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}

	.logo {
		height: 200upx;
		width: 200upx;
		margin-top: 200upx;
		margin-left: auto;
		margin-right: auto;
		margin-bottom: 50upx;
	}

	.text-area {
		display: flex;
		justify-content: center;
	}

	.title {
		font-size: 36upx;
		color: #8f8f94;
	}
</style>
