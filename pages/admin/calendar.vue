<template>
	<div>
		<el-row style="margin-bottom: 16px;">
			<el-col>
				<h3 style="color: #50649C;font-weight: 500;float: left;">Dashboard</h3>
				<el-breadcrumb separator-class="el-icon-arrow-right" style="float: right;">
				  <el-breadcrumb-item :to="{ path: '/' }" ><span style="color: #92A5C5;font-weight: 500;">Homepage</span></el-breadcrumb-item>
				  <el-breadcrumb-item><span style="color: #92A5C5;font-weight: 500;">Calendar</span></el-breadcrumb-item>
				</el-breadcrumb>
			</el-col>	
		</el-row>
		<el-row :gutter="10">
		  <el-col :xs="24" :sm="24" :md="18" :lg="16" :xl="16">
		  	<el-row>
			  	<el-card class="box-card" style="margin-top: 12px;">
				  <span style="color: #50649C;font-weight: 500;">Full Width Calender</span>
				  <div style="margin-top: 16px;">
				   <v-calendar is-expanded :attributes='attrs'></v-calendar>
				  </div>
				</el-card>
			</el-row>
		  </el-col>
		  <el-col :xs="24" :sm="24" :md="6" :lg="8" :xl="8">
		  	<el-card class="box-card" style="margin-top: 12px;">
		  		<span style="color: #50649C;font-weight: 500;">Multiple Date Picker</span>
		  		<div style="margin-top: 16px;">
		  			<v-date-picker
					  v-model="dates"
					  mode="multiple"
					  is-inline is-expanded
					  />
		  		</div>
		  	</el-card>
		  </el-col>
		</el-row>
		<el-row :gutter="10">
		  <el-col :xs="24" :sm="24" :md="18" :lg="16" :xl="16">
		  	<el-row>
			  	<el-card class="box-card" style="margin-top: 12px;">
				  <span style="color: #50649C;font-weight: 500;">Full Width Dark Calender</span>
				  <div style="margin-top: 16px;">
				   <v-calendar is-expanded is-dark :attributes='attrs'></v-calendar>
				  </div>
				</el-card>
			</el-row>
		  </el-col>
		  <el-col :xs="24" :sm="24" :md="6" :lg="8" :xl="8">
		  	<el-card class="box-card" style="margin-top: 12px;">
		  		<span style="color: #50649C;font-weight: 500;">Multiple Date Picker Dark</span>
		  		<div style="margin-top: 16px;">
		  			<v-date-picker
					  v-model="dates"
					  mode="multiple"
					  is-inline is-dark is-expanded
					  />
		  		</div>
		  	</el-card>
		  </el-col>
		</el-row>
	</div>
</template>
<script>
	export default{
		layout: 'AdminLayout',
	    data() {
	      return{
             dates: [new Date(2018, 0, 9), new Date(2018, 0, 25)], 
             attrs: [
		        {
		          key: 'today',
		          popover: {label: 'Holiday'},
		          highlight: 'indigo',
		          dates: new Date(),
		        },
		      ],  
	      }
	    }
	}
</script>