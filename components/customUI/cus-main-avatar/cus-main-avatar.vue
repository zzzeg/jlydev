<template>
	<div class="cus_main_avatar">
		<div class="avatars hastxk" :class="{txkname}"><!--hastxk:头像框-->
			<image :src="avatar || 'https://tvax1.sinaimg.cn/crop.0.179.1080.1080.180/0088ROfVly1gf605n2vxbj30u013z4g9.jpg'"></image>
		</div>
		<div class="title">{{ title }}</div>
		<div v-if="subtitle!= ''" class="subtitle">{{ subtitle }}</div>
		<div v-if="time!= ''" class="time">{{ time }}</div>
		<div v-if="btnValue != ''" class="btn" :class="{'blodfont':btnfontWeight}" @click="btnclick">{{ btnValue }}</div>
		<div v-if="gender !=''" class="level woman" :class="{'blue':gender == 'man'}">
			{{ gender == 'man' ? '壕' : '魅' }} {{ level }}
		</div>
	</div>
</template>

<script>
	export default{
		name: 'customavatar',
		emits: ['clickItem'],
		props: {
			avatar: {
				type:String,
				default: ''
			},
			txkname: {
				type: String,
				default: 'xxx'
			},
			title: {
				type: String,
				default: ''
			},
			subtitle: {
				type: String,
				default: ''
			},
			time: {
				type: String,
				default: ''
			},
			btnCanClick: {
				type: Boolean,
				default: false
			},
			btnValue: {
				type: String,
				default: ''
			},
			btnfontWeight: {
				type: Boolean,
				default: false
			},
			gender: {
				type: String,
				default: ''
			},
			level: {
				type: String,
				default: ''
			}
		},
		data() {
			return {
				
			}
		},
		methods: {
			clickItem(item) {
				this.$emit('clickItem', item)
			},
			btnclick() {
				if(this.btnCanClick) {
					this.$emit('btnclick')
				}
			}
		}
	}
</script>

<style lang="scss" scoped>
	.cus_main_avatar{
		border-radius: 20rpx; background: #eeeeee; text-align: center; padding:20rpx 0 6rpx 0;
		.avatars{ padding:10rpx;
			image{ width:12vw; height:12vw; border-radius: 12vw; }
		}
		.title{ font-size:24rpx;font-weight: 500; white-space: nowrap;overflow: hidden;text-overflow: ellipsis; line-height: 2; }
		.subtitle,.time{ font-size:20rpx; color:#666; line-height: 1.5; }
		.btn{ width:4em; color:#fff; line-height: 1.2; font-size:24rpx; border-radius: 10rpx; background: #000; margin:0 auto;
			&.blodfont{
				font-weight: bold;
			}
		}
		.level{ 
			width:3em; margin:10rpx auto; border-radius: 10rpx;line-height: 1.2; 
			&.woman{
				color:#000;
				background:yellow;
			}
			&.man{
				color:#fff;
				background: blue;
			}
		}
	}
</style>