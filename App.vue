<script>
	export default {
		onLaunch: function() {
			console.log('App Launch')
		},
		onShow: function() {
			console.log('App Show')
		},
		onHide: function() {
			console.log('App Hide')
		}
	}
</script>

<style>
	/*每个页面公共css */
	body{font-size:24rpx; color:#444;}
	.u-f-ac{display: flex; align-items: center;}
	.u-f-acjsa{ display: flex; align-items: center; justify-content: space-around; }
	.u-f-acjsb{ display: flex; align-items: center; justify-content: space-between; }
</style>
