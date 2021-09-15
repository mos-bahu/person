<template>
	<view class="user">
		<scroll>
			<template #scroll>
				<view class="">
					<i>aa</i>
				</view>
				<!-- 头像部分 -->
				<view class="user-image">
					<i></i>
					<image src="../../static/logo.png" mode=""></image>
					<text>霸虎</text>
				</view>
				<!-- 关注部分 -->
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
				<!-- 个人收藏 -->
				<view class="my-Love">
					<view class="">
						<text></text>
						<text></text>
					</view>
					<scroll-view :scroll-top="scrollTop" scroll-y="true" class="scroll-x" @scrolltoupper="upper"
						@scrolltolower="lower" @scroll="scroll">
						<view id="demo1" class="scroll-view-item uni-bg-red">A</view>
						<view id="demo2" class="scroll-view-item uni-bg-green">B</view>
						<view id="demo3" class="scroll-view-item uni-bg-blue">C</view>
					</scroll-view>
				</view>
				<!-- 个人中心 -->
				<view class="">
					<view v-for="(item,index) in ['我的消息','我的私信','提问箱','我的喜欢','历史浏览', '主题',' ',' ',' ']" :key=" index">
						<view class="">
							<text>{{item}}</text>
						</view>
					</view>
				</view>
				<!-- 创作中心 -->
				<view class="">
					<view v-for="(item,index) in ['我的创作','热门活动','草稿箱','回收箱','我的统计']" :key="index">
						<view class="">
							<text>{{item}}</text>
						</view>
					</view>
				</view>
			</template>
		</scroll>
	</view>
</template>

<script>
	import scroll from '../common/scroll/scroll.vue';
	export default {
		data() {
			return {
				scrollTop: 0,
				old: {
					scrollTop: 0
				}
			}
		},
		components: {
			scroll
		},
		methods: {
			upper: function(e) {
				console.log(e)
			},
			lower: function(e) {
				console.log(e)
			},
			scroll: function(e) {
				console.log(e)
				this.old.scrollTop = e.detail.scrollTop
			},
			goTop: function(e) {
				this.scrollTop = this.old.scrollTop
				this.$nextTick(() => {
					this.scrollTop = 0
				});
				uni.showToast({
					icon: "none",
					title: "纵向滚动 scrollTop 值已被修改为 0"
				})
			}
		}
	}
</script>

<style scoped>
	@import url("");
</style>
