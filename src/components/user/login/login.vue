<template>
	<div class="login">
		<div class="login_content">
			<div class="login_select">
				<span class="s_singin" :class="{ active: status === 0 }" @click="loginMode">登录</span>
				<span class="s_register" :class="{ active: status !== 0 }" @click="registerMode">注册</span>
			</div>
			<div class="singin">
				<div class="block_area">
					<label for="userName">username</label>
					<input type="text" id="userName" placeholder="请输入用户名">
				</div>
				<div class="block_area">
					<label for="userPwd" >password</label>
					<input type="password" id="userPwd" placeholder="请输入密码">
				</div>
				<input type="button" value="登录">
			</div>
		</div>
	</div>
</template>
<script>
	export default{
		data () {
			return {
				// 0 是登录  1是注册
				status: 0
			}
		},
		methods: {
			loginMode () {
				this.status = 0
			},
			registerMode () {
				this.status = 1
			}
		}
	}
</script>
<style lang="stylus" rel="stylesheet/stylus">
@import '~common/stylus/global.styl'
	.login
		position: fixed
		top: 0
		left: 0
		bottom: 0
		right: 0
		background: rgba(0,0,0,0.6);
		.login_content
			position:absolute
			top: 50%
			left:50%
			width: 90%
			min-height: 300px
			max-width: 340px
			padding: 15px 0px
			transform: translate3d(-50%,-50%,0)
			background: rgba(0,0,0,0.4)
			.login_select
				width: 100%
				height: 48px
				line-height: 48px
				font-size: 0
				padding: 0 5px
				box-sizing: border-box
				span
					display:inline-block
					font-size: 16px
					color: #fff
					width: 50%
					text-align:center
					vertical-align:middle
					position:relative
					cursor: pointer
					&.active
						&:before
							content: ''
							width: 30%
							height: 2px 
							background: #fff
							position: absolute
							bottom: 0
							left: 50%
							transform: translate3d(-50%,0,0)
			.singin
				box-sizing: border-box
				padding: 20px 20px
				.block_area
					margin: 10px 0 20px 0
				label,input
					display: block
				label
					color: #e1e1e1
				input[type='text'],input[type='password']
					background: transparent
					// border: 1px solid #eee
					outline:none
					height: 32px
					width: 100%
					border-radius: 2px
					color: #fff
					text-indent: 4px
					border: none
					border-bottom: 1px solid #aaa
					&:focus
						border-bottom: 1px solid #fff
				input[type='button']
					background: $com_button_color
					border: 1px solid $com_button_color
					height: 32px
					width: 100%
					border-radius: 2px
					color: #fff
					height: 36px
					line-height: 36px
					margin-top: 30px
					margin-bottom: 10px
					outline:none
					cursor: pointer
					&:hover
						background: $com_button_active_color
					
</style>