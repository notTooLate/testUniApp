<script>
export default {
	//当uni-app 初始化完成时触发
	onLaunch: function() {
		console.log('App Launch');
		// #ifdef APP-PLUS
		// 锁定屏幕方向
		plus.screen.lockOrientation('portrait-primary'); //锁定
		// 检测升级
		/* uni.request({
			url: 'https://uniapp.dcloud.io/update', //检查更新的服务器地址
			data: {
				appid: plus.runtime.appid,
				version: plus.runtime.version,
				imei: plus.device.imei
			},
			success: (res) => {
				console.log('success', res);
				if (res.statusCode == 200 && res.data.isUpdate) {
					let openUrl = plus.os.name === 'iOS' ? res.data.iOS : res.data.Android;
					// 提醒用户更新
					uni.showModal({
						title: '更新提示',
						content: res.data.note ? res.data.note : '是否选择更新',
						success: (showResult) => {
							if (showResult.confirm) {
								plus.runtime.openURL(openUrl);
							}
						}
					})
				}
			}
		}) */
		// #endif
	},
	//当 uni-app 启动，或从后台进入前台显示
	onShow: function() {
		console.log('App Show');
	},
	//当 uni-app 从前台进入后台
	onHide: function() {
		console.log('App Hide');
	}
};
</script>

<style>
/* uni.css - 通用组件、模板样式库，可以当作一套ui库应用 */
@import './common/uni.css';
@import './common/iconfont.css';
@import './common/font-awesome.min.css';

/* uni-app默认全局使用flex布局。因为flex布局有利于跨更多平台，尤其是采用原生渲染的平台。如不了解flex布局，请参考http://www.w3.org/TR/css3-flexbox/。如不使用flex布局，请删除或注释掉本行。*/
body,
page {
	/* uni-page */
	height: 100%;
	min-height: 100%;
	display: flex;
}

/* #ifdef MP-BAIDU */
page {
	width: 100%;
	height: 100%;
	display: block;
}
swan-template {
	width: 100%;
	min-height: 100%;
	display: flex;
}
/* #endif */

/* uni-page-body */
uni-page-body {
}

.page-content {
	width: 100%;
}
.uni-page-head-bd {
	left: 60upx !important;
	right: 60upx !important;
}
.uni-page-head .uni-page-head__title {
	font-weight: 100;
}
.content {
	display: flex;
	flex: 1;
	flex-direction: column;
	padding: 20upx;
}

/* 登录、注册、找回密码 */
.input-group {
	background-color: #ffffff;
	margin-top: 40upx;
	position: relative;
}

.input-group::before {
	position: absolute;
	right: 0;
	top: 0;
	left: 0;
	height: 1upx;
	content: '';
	-webkit-transform: scaleY(0.5);
	transform: scaleY(0.5);
	background-color: #c8c7cc;
}

.input-group::after {
	position: absolute;
	right: 0;
	bottom: 0;
	left: 0;
	height: 1upx;
	content: '';
	-webkit-transform: scaleY(0.5);
	transform: scaleY(0.5);
	background-color: #c8c7cc;
}

.input-row {
	display: flex;
	flex-direction: row;
	position: relative;
}

.input-row .title {
	width: 20%;
	height: 50upx;
	min-height: 50upx;
	padding: 15upx 0;
	padding-left: 30upx;
	line-height: 50upx;
}

.input-row.border::after {
	position: absolute;
	right: 0;
	bottom: 0;
	left: 15upx;
	height: 1upx;
	content: '';
	-webkit-transform: scaleY(0.5);
	transform: scaleY(0.5);
	background-color: #c8c7cc;
}

.btn-row {
	margin-top: 50upx;
	padding: 20upx;
}

button.primary {
	background-color: #0faeff;
	line-height: 1.8;
}
</style>
