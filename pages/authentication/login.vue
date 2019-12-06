<template>
	<div class="app"> 
		<el-container class="form">
			<el-row>
          <el-col :span="24">
            <div class="logo">
              <img src="~assets/nuxt-logo-d.png" width="50px">
            </div>
            <div>
              <p class="title-head">Welcome Back !</p>
              <p class="title-sub">Sign in to continue to Nuxtjs Admin</p>
            </div>
            <div class="form-div">
              <el-form ref="form" size="mini">
                <el-form-item >
                  <el-input placeholder="Email" type="email" v-model="email"></el-input>
                </el-form-item>
                <el-form-item >
                  <el-input placeholder="Password" type="password" v-model="password"></el-input>
                </el-form-item>
                <el-form-item >
                   <el-checkbox v-model="checked"><span class="remember">Remember me</span></el-checkbox> <span class="forgot-pw">Forgot Password ?</span>
                </el-form-item>
                <el-form-item size="large" style="display: flex;justify-content: center;">
                  <el-button class="submit-btn" round >Sign In</el-button>

                </el-form-item>
              </el-form>
            </div>
          </el-col>   
      </el-row>
		</el-container>
	</div>
</template>
<script>
	export default{
		layout : 'AuthLayout',
    data(){
      return{
        email:'',
        password:'',
        checked:false,
      }
    }
	}
</script>
<style >
 .el-container{
  	font-family:Poppins,sans-serif;
  }
  .app{
  	display: flex;
  	flex-direction: column;
  	align-items: center;
  	justify-content: center;
  	height: 100vh;
  }
  .form{
  	display: flex;
  	flex-direction: column;
  	align-items: center;
  	justify-content: center;
  }
  .login-title{
    text-align: center;
    color: white;
  }
  .title-head{
    font-size: 24px;
    color: #F2F6FC;
    text-align: center;
  }
  .title-sub{
    font-size: 12px;
    color: #F2F6FC;
    text-align: center;
  }
  .logo{
    display: flex;
    justify-content: center;
  }
  .form-div{
    width: 300px;
    margin-top: 30px;
  }
  .submit-btn{
    background-color: #010312;
    border: 1px solid #0D5087;
    color: #F2F6FC;
  }
  .submit-btn:hover{
    background-color: #010312;
    border: 1px solid #0d6cba;
    color: #F2F6FC;
  }
 .submit-btn:focus{
    background-color: #010312;
    border: 1px solid #0d6cba;
    color:#F2F6FC;
  }
  .remember{
    color: #F2F6FC;
    font-size: 12px;
    font-weight: 200;
  }
  .forgot-pw{
    float: right;
    color: #F2F6FC;
    font-size: 12px;
    font-weight: 200;
  }
</style>