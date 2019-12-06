<template>
	<el-container style="height: 100vh; ">
	  <el-aside :width="asideWidth" style="background-color: #181823" class="hidden-sm-and-down">
	    <el-menu  background-color="#181823"
      text-color="#7EA8B3"
      active-text-color="#5696F8" :collapse="isCollapse" class="el-menu-vertical-demo">
          <el-menu-item >
		    <img src="~assets/logo.png" width="18px">
		    <span slot="title">Nuxt Admin</span>
		  </el-menu-item>
		  <nuxt-link to="/admin/dashboard" style="text-decoration: none;">
			  <el-menu-item index="0.1">
			    <i class="el-icon-menu" style="color: #5696F8"></i>
			    <span slot="title">Dashboard</span>
			  </el-menu-item>
		  </nuxt-link>
		  <nuxt-link to="/admin/calendar" style="text-decoration: none;">
			  <el-menu-item index="0.2" :to="{ path: '/admin/calendar' }">
			    <i class="el-icon-date" style="color: #5696F8"></i>
			    <span slot="title">Calender</span>
			  </el-menu-item>
		  </nuxt-link>
	      <el-submenu index="1">
		    <template slot="title">
		      <i class="el-icon-lock" style="color: #5696F8"></i>
		      <span slot="title">Authentication</span>
		    </template>
		    <el-menu-item-group>
		    <nuxt-link to="/authentication/login" style="text-decoration: none;">	
		      <el-menu-item index="1-1">Login Page</el-menu-item>
		    </nuxt-link>
		      <el-menu-item index="1-2">item two</el-menu-item>
		    </el-menu-item-group>
		  </el-submenu>
		  <el-menu-item index="2">
		    <i class="el-icon-menu" style="color: #5696F8"></i>
		    <span slot="title">Navigator Two</span>
		  </el-menu-item>
		  <el-menu-item index="3" disabled>
		    <i class="el-icon-document" style="color: #5696F8"></i>
		    <span slot="title">Navigator Three</span>
		  </el-menu-item>
		  <el-menu-item index="4">
		    <i class="el-icon-setting" style="color: #5696F8"></i>
		    <span slot="title">Navigator Four</span>
		  </el-menu-item>
	    </el-menu>
	  </el-aside>
	  
	  <el-container>
	    <el-header style="padding-right: 0px;padding-left: 0px;">
			<el-menu
			  class="el-menu-demo"
			  mode="horizontal"
			  background-color="#fff"
			  text-color="#ABB6CE"
			  active-text-color="#ABB6CE" style="width: 100%;">
			  <el-menu-item index="1" @click="toggleSideBar"  background-color="#fff"><i class="fas fa-bars" ></i></el-menu-item>
			</el-menu>
	    </el-header>
	    
	    <el-main style="background-color:#EAF0F7;">
	      <nuxt/>
	    </el-main>
	    <el-footer><span style="float: left;"><i class="far fa-copyright"></i> Copyright 2020</span>Designed with <i class="fas fa-heart" style="color: #F1646C;"></i> by Algorizon Technologies</el-footer>
	  </el-container>
	</el-container>
</template>
<style>
  .el-header {
    background-color: #fff;
    color: #FFFFFF;
    line-height: 60px;
  }
  .el-container{
  	font-family:Poppins,sans-serif;
  }
  .el-aside {
    
  }
  .el-menu-vertical-demo:not(.el-menu--collapse) {
    width: 220px;
  }
 .el-footer {
 	border-top: 0.2px solid #92A5C5;
    background-color:#EAF0F7;
    color: #50649C;
    text-align: center;
    line-height: 60px;
    font-size: 12px;
  }
</style>

<script>
  export default {
    data() {
      return {
        activeIndex: '1',
        activeIndex2: '1',
        isCollapse:false,
        asideWidth:'220px',
      };
    },
    methods:{
    	toggleSideBar(){
    		if(this.isCollapse){
    			this.asideWidth = '220px';
    		}else{
    			this.asideWidth = '60px';
    		}
    		this.isCollapse = !this.isCollapse;
    		
    	}
    }
  };
</script>