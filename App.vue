
<script>
	export default {
		onLaunch: function() {
			uni.getSystemInfo({
				success:function(e){
				global.statusBar=e.statusBarHeight;
				if(e.platform='android')
				{
					global.customBar=e.statusBarHeight+50
				}else
				{
					global.customBar=e.statusBarHeight+45
				}
				}
			})
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
</style>
