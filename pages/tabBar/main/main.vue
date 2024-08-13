<template>
	<div class="cont">
		<uni-nav-bar left-icon="left" :border="false" background="none" dark title="乐园" class="navbar pdLR30" status-bar fixed="true">
			<template v-slot:left>
				<div class="bar-left">
					<uni-icons type="search" size="22" color="#fff"></uni-icons>
				</div>
			</template>
			<template v-slot:right>
				<div class="bar-right">
					每日签到
				</div>
			</template>
		</uni-nav-bar>
		
		<div class="model4 pdLR30 u-f-ac">
			<div class="models" v-for="(item, index) in models" :key="index" @click="navto(item.navto)">
				<image :src="item.imgsrc"></image>
				<div class="text">{{ item.text }}</div>
			</div>
		</div>
		
		<div class="swiper1">
			<swiper class="swiper-box" autoplay="true" circular="true">
				<swiper-item class="swiperitem" v-for="(item, index) in swiperlist" :key="index">
					<image :src="item.imgsrc" mode="widthFix"></image>
				</swiper-item>
			</swiper>
		</div>
		
		<div class="userblock high_user">
			<div class="title u-f-ac">
				<div class="left u-f-ac">
					优质推荐 <div class="text">优质用户关注ta</div>
				</div>
				<div class="right">
					<uni-icons type="refreshempty" size="12" color="#3c9fcc"></uni-icons> 换一批
				</div>
			</div>
			<scroll-view scroll-x="true" class="scrollviewX">
				<div class="useritem" v-for="(item, index) in highuser" :key="index">
					<cus-main-avatar 
					:title="item.name" 
					:avatar="item.avatar"
					:btnValue="item.btnValue"
					:btnfontWeight="true"
					:gender="item.gender"
					:level="item.level"
					>
					</cus-main-avatar>
				</div>
			</scroll-view>
		</div>
		
		<div class="main_open_vip">
			<image src="/static/images/main/main_vip.png" mode="widthFix" style="width: 100%;"></image>
		</div>
		
		<div class="userblock high_user">
			<div class="title u-f-ac">
				<div class="left u-f-ac">
					正在活跃 <div class="text">实时在线 随时可撩</div>
				</div>
				<div class="right">
					<uni-icons type="refreshempty" size="12" color="#3c9fcc"></uni-icons> 查看更多
				</div>
			</div>
			<scroll-view scroll-x="true" class="scrollviewX">
				<div class="useritem" v-for="(item, index) in highuser" :key="index">
					<cus-main-avatar 
					:title="item.name" 
					:avatar="item.avatar"
					:btnValue="item.btnValue"
					:btnfontWeight="true"
					:gender="item.gender"
					:level="item.level"
					>
					</cus-main-avatar>
				</div>
			</scroll-view>
		</div>
		
	</div>
</template>

<script lang="ts" setup>
	import {ref, reactive} from 'vue'
	const models = reactive([{
		imgsrc: 'https://coffer-cdn.bainuo.cn//useravatar-pub/ee/ee1d1f41b100f60b87a41769e678b5e5.png',
		text: '乐园商城',
		navto: ''
	},{
		imgsrc: 'https://coffer-cdn.bainuo.cn//useravatar-pub/ee/ee1d1f41b100f60b87a41769e678b5e5.png',
		text: '牵红线',
		navto: ''
	},{
		imgsrc: 'https://coffer-cdn.bainuo.cn//useravatar-pub/ee/ee1d1f41b100f60b87a41769e678b5e5.png',
		text: '分享乐园',
		navto: ''
	},{
		imgsrc: 'https://coffer-cdn.bainuo.cn//useravatar-pub/ee/ee1d1f41b100f60b87a41769e678b5e5.png',
		text: '防骗指南',
		navto: ''
	}])
	
	
	const swiperlist = reactive([{
		imgsrc: '/static/images/main/swiper_01.png'
	},{
		imgsrc: '/static/images/main/swiper_02.png'
	}])
	
	const highuser = reactive([{
		name: '徐糯',
		avatar: '',
		btnValue: 'M',
		btnfontWeight: true,
		gender: 'woman',
		level: '3'
	},{
		name: '徐糯',
		avatar: '',
		btnValue: 'M',
		btnfontWeight: true,
		gender: 'woman',
		level: '3'
	}])
	
	const navto = (src)=>{
		uni.navigateTo({
			url: src
		})
	}
</script>

<style lang="scss" scoped>
	.cont{ background: url('/static/images/main/bg.png') repeat-x top; background-size: 100% 25vh; background-attachment:fixed;
		height:100%; overflow:auto;
	}
	.pdLR30{ padding:0 30rpx; }
	.navbar{ 
		::v-deep .uni-navbar--fixed{
			background: url('/static/images/main/bg.png') repeat-x top; background-size: 100% auto;
		}
	}
	.model4{
		justify-content: space-around; align-items: center; color:#fff; padding: 20rpx 0;
		.models{
			text-align: center;
			image{ width:18vw; height:10vw; border-radius:40rpx;}
		}
	}
	.swiper1{
		margin-bottom:-20rpx;
		.swiperitem{ 
			text-align: center;
			image{ width:90vw; height:30vw;}
		}
	}
	.userblock{
		.title{
			justify-content: space-between; margin-bottom:20rpx; padding:0 30rpx;
			.left{
				font-size:32rpx; font-weight: 500; align-items: baseline;
				.text{
					color:#9f9f9f; font-size:20rpx; margin-left:10rpx; font-weight: normal;
				}
			}
			.right{
				background:#d9f5ff; border-radius:40rpx; color:#3c9fcc; font-size:20rpx; display:flex; align-items: center; padding:0 20rpx; transform: scale(.8);
			}
		}
		.scrollviewX{ white-space: nowrap; width: 100%;
			::-webkit-scrollbar{
				display: none;
			}
			.useritem{ width:calc(25vw - 28rpx); margin-left:16rpx; display: inline-block; 
				&:first-child{ margin-left:30rpx; }
			}
		}
	}
	
	.main_open_vip{ padding:20rpx 30rpx; }
</style>