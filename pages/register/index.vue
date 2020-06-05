<template>
	<view class="content">
		<view class="navigation-bar" :style="{height:height+'px'}">
		</view>
		
		<view class="icon-text">
			<image src="./icon/icon.jpeg" class="app-icon"></image>
			<view class="text">
				注册
			</view>
		</view>
		
		<view class="login-form">
			<view class="phone-name">
				<image src="./icon/手机.png" mode="aspectFit" class="phone-icon"></image>
				<input type="text" :value="loginForm.username"  class="phone-iput" placeholder="请输入手机号码" @focus="focusColorName"  @blur="blurColorName">
				<view class="line" :class="isfocusName?'blue':'gray'">
				</view>
			</view>
			
			<view class="code-input">
				<image src="./icon/保护.png"  mode="aspectFit" class="password-icon"></image>
				<input type="text"   :value="loginForm.password" class="pwd-iput" placeholder="请输入验证码" @focus="focusColorCode"  @blur="blurColorCode">
					<text class="code">获取验证码</text>
				<view class="line" :class="isfocusCode?'blue':'gray'"></view>
			</view>
			
			<view class="password">
				<image src="./icon/锁.png"  mode="aspectFit" class="password-icon"></image>
				<input :type="pwdType"   :value="loginForm.password" class="pwd-iput" placeholder="请输入密码" @focus="focusColorPwd"  @blur="blurColorPwd">
			
				<view class="line" :class="isfocusPwd?'blue':'gray'">
				</view>
			</view>
			
		
		</view>
		
		<view class="login-button__register">
			<view class="button-login">
				 注册
			</view>
			<view class="login-text">
				<text class="no-account">点击注册意味着您同意</text>
				<text class="register-now">《用户协议》</text>
			</view>	
		</view>
		
	</view>
</template>

<script>
	export default {
		data() {
			return {
				height: 0,
				loginForm:{
					username:'',
					password:''
				},
				isfocusName:false,
				isfocusPwd:false,
				isfocusCode:false,
				pwdType:'password'
			}
		},
		onLoad() {
			this.height = global.customBar
		},
		methods: {
            focusColorName()
			{
				this.isfocusName=true;		
			},
			blurColorName()
			{
			this.isfocusName=false;
			},
			focusColorCode()
			{
				this.isfocusCode=true;		
			},
			blurColorCode()
			{
			this.isfocusCode=false;
			},
			focusColorPwd()
			{
				this.isfocusPwd=true;		
			},
			blurColorPwd()
			{
			this.isfocusPwd=false;
			},
			changeType()
			{
				if(this.pwdType=='password')
				{
					this.pwdType='text'
				}else
				{
					this.pwdType='password'
				}	
			}
		}
	}
</script>

<style>
	.content {
		display: flex;
		flex-direction: column;
	}

	.navigation-bar {
		width: 100%;
		background-color: red;
		position: relative;
	}
	.icon-text
	{
		width: 100%;
		height: 360rpx;
		position: relative;
	}
	.app-icon{
		width: 160rpx;
		height: 160rpx;
		border-radius: 20rpx;
		position: absolute;
		left: 50%;
		transform: translateX(-50%);
		top: 60rpx;
	}
	.text{
		transform: translateX(-50%);
		left: 50%;
		position: absolute;
		bottom: 40rpx;
		font-size: 46rpx;
		font-weight: 400;
	}
	.login-form{
		width: 100%;
	}
	.phone-name{
		height: 140rpx;
		width: 100%;
		position: relative;
	}
	.phone-icon{
		width: 45rpx;
		height: 45rpx;
		position: absolute;
		top: 50%;
		transform: translateY(-50%);
		left: 30rpx;
	}
	.phone-iput{
		position: absolute;
		top: 50%;
		transform: translateY(-50%);
		left: 100rpx;
	}
	.line{
		position: absolute;
		bottom: 0rpx;
		height: 2rpx;
		width: 670rpx;
		transform: translateX(-50%);
		left: 50%;
	}
	.code-input{
		position: relative;
		width: 100%;
		height: 160rpx;
	}
	
	.password{
		position: relative;
		height: 160rpx;
		width: 100%;
	}
	.password-icon{
		width: 45rpx;
		height: 45rpx;
		position: absolute;
		left: 30rpx;
		top: 70rpx;
	}
	.pwd-iput{
		position:absolute ;
		left: 100rpx;
		top: 70rpx;
	}
	
	.code{
		position: absolute;
		width: 220rpx;
		height: 70rpx;
		line-height: 70rpx;
		font-size: 28rpx;
		border-radius: 110rpx;
		color: #FFFFFF;
		text-align: center;
		background-color: #007AFF;
		top: 50%;
		transform: translateY(-40%);
		right: 40rpx;
	}
	
	.login-button__register{
		width: 100%;
		position: relative;
	}
	.button-login{
		width: 600rpx;
		height: 100rpx;
		top: 120rpx;
		border-radius: 60rpx;
		position: absolute;
		transform: translateX(-50%);
		left: 50%;
		text-align: center;
		line-height: 100rpx;
		background-color: #007AFF;
		color: #FFFFFF;
	}
	.login-text{
		position: absolute;
		top: 260rpx;
		transform: translateX(-50%);
		left: 50%;
		width: 600rpx;
		text-align: center;
		font-size: 32rpx;
		
	}
	.no-account{
		color: #808080;
	}
	.register-now{
		color: #007AFF;
	}
	.blue{
		background-color:#007AFF
	}
	.gray{
		background-color:#BFBFBF
	}
</style>

