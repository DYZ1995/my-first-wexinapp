<template>
	 <view class="content">
		 <view class="title">{{title}}......</view>
		 <view class="area-content">
			 <rich-text :nodes="newsContents"></rich-text>
		 </view>
	 </view>
</template>

<script>
	export default {
		data() {
			return {
				title: '',
				newsContents: ''
			}
		},
		onLoad(params) {
			uni.request({
				url: "https://unidemo.dcloud.net.cn/api/news/36kr/"+params.newsId,
				method:'GET',
				data:{},
				success: res => {
					console.log(res);
					this.title = res.data.title;
					this.newsContents = res.data.content;
				},
				fail: () => {},
				complete: () => {}
			})
		},
		methods: {
			
		}
	}
</script>

<style>
.content{padding:10upx 2%; width: 96%; flex-wrap:wrap;}
.title{line-height:2em; font-weight:700; font-size:38upx;}
.art-content{line-height:2em;}
</style>
