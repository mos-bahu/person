<template>
	<view class="user">
		<view class="user-image">
			<image src="../../static/logo.png" mode=""></image>
			<text>霸虎</text>
		</view>
		<view class="user-nubmer">
			<view v-for="(item,index) in ['关注','粉丝','获赞']" :key="index">
				<view class="title">
					1
				</view>
				<view class="fan-number">
					{{item}}
				</view>
			</view>
		</view>
	    <view></view>
	</view>
</template>

<script>
</script>

<style>
</style>
