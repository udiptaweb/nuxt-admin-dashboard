<template>
	<div>
		<el-row style="margin-bottom: 16px;">
			<el-col>
				<h3 style="color: #50649C;font-weight: 500;float: left;">Dashboard</h3>
				<el-breadcrumb separator-class="el-icon-arrow-right" style="float: right;">
				  <el-breadcrumb-item :to="{ path: '/' }" ><span style="color: #92A5C5;font-weight: 500;">Homepage</span></el-breadcrumb-item>
				  <el-breadcrumb-item><span style="color: #92A5C5;font-weight: 500;">Dashboard</span></el-breadcrumb-item>
				</el-breadcrumb>
			</el-col>	
		</el-row>
		<el-row :gutter="10">
		  <el-col :xs="24" :sm="24" :md="18" :lg="16" :xl="16">
		  	<el-row>
			  	<el-card class="box-card" style="margin-top: 12px;">
				  <span style="color: #50649C;font-weight: 500;">Visitors Statistics</span>
				  <div >
				    <la-cartesian narrow :bound="[0]" :data="values">
					    <la-bar label="pv" prop="pv"></la-bar>
					    <la-line label="uv" prop="uv"></la-line>
					    <la-area label="amt" prop="amt"></la-area>

					    <la-x-axis gridline dashed prop="name"></la-x-axis>
					    <la-y-axis gridline dashed></la-y-axis>
					    <la-tooltip></la-tooltip>
					    <la-legend selectable></la-legend>
					    <la-y-marker dashed :value="4000" label="marker"></la-y-marker>
					</la-cartesian>
				  </div>
				</el-card>
			</el-row>
		  </el-col>
		  <el-col :xs="24" :sm="24" :md="6" :lg="8" :xl="8">
		  	<el-card class="box-card" style="margin-top: 12px;">
		  		<span style="color: #50649C;font-weight: 500;">Impressions</span>
		  		<la-cartesian :bound="[0, n => n + 100]" :data="values2" :width="350" :height="300">
				    <la-area dot curve prop="pv"></la-area>
				    <la-x-axis prop="name"></la-x-axis>
				    <la-y-axis></la-y-axis>
				</la-cartesian>
		  	</el-card>
		  </el-col>
		</el-row>
		<el-row :gutter="10" style="margin-top: 16px;">
		  <el-col :xs="24" :sm="24" :md="6" :lg="6" :xl="6">
		  	<el-card class="box-card" style="margin-top: 12px;">
		  		<el-tag size="mini">Sessions</el-tag>
		  		<p style="color: #50649C;font-weight: 500;">24K</p>
		  		<p><small><span style="color: #67C23A;"><i class="fas fa-chart-line"></i> 8.5%</span> <span style="color:  #92A5C5;">New Sessions Today</span></small></p>
		  	</el-card>
		  </el-col>
		  <el-col :xs="24" :sm="24" :md="6" :lg="6" :xl="6">
		  	<el-card class="box-card" style="margin-top: 12px;">
		  		<el-tag size="mini" type="success">Avg Sessions</el-tag>
		  		<p style="color: #50649C;font-weight: 500;">00:30</p>
		  		<p><small><span style="color: #F56C6C;"><i class="fas fa-chart-line"></i> 2.5%</span> <span style="color:  #92A5C5;">Weekly Avg.Sessions</span></small></p>
		  	</el-card>
		  </el-col>
		  <el-col :xs="24" :sm="24" :md="6" :lg="6" :xl="6">
		  	<el-card class="box-card" style="margin-top: 12px;">
		  		<el-tag size="mini" type="warning">Bounce Rate</el-tag>
		  		<p style="color: #50649C;font-weight: 500;">Rs. 90000</p>
		  		<p><small><span style="color: #F56C6C;"><i class="fas fa-chart-line"></i> 5.5%</span> <span style="color:  #92A5C5;">Bounce Rate Weekly</span></small></p>
		  	</el-card>
		  </el-col>
		  <el-col :xs="24" :sm="24" :md="6" :lg="6" :xl="6">
		  	<el-card class="box-card" style="margin-top: 12px;">
		  		<el-tag size="mini" type="danger">Goal Completions</el-tag>
		  		<p style="color: #50649C;font-weight: 500;">10000</p>
		  		<p><small><span style="color: #67C23A;"><i class="fas fa-chart-line"></i> 13.5%</span> <span style="color:  #92A5C5;">Completions Weekly</span></small></p>
		  	</el-card>
		  </el-col>
		</el-row>
		<el-row :gutter="10">
		  <el-col :xs="24" :sm="24" :md="24" :lg="12" :xl="12">
		  	<el-row>
			  	<el-card class="box-card" style="margin-top: 12px;">
				  <span style="color: #50649C;font-weight: 500;">Recent Registrations</span>
				  <div >
				    <el-table
					    :data="tableData"
					    style="width: 100%;font-size: 12px;">
					    <el-table-column
					      label="Date"
					      >
					      <template slot-scope="scope">
					        <i class="el-icon-time"></i>
					        <span style="margin-left: 10px">{{ scope.row.date }}</span>
					      </template>
					    </el-table-column>
					    <el-table-column
					      label="Name"
					      >
					      <template slot-scope="scope">
					        <el-popover trigger="hover" placement="top">
					          <p>Name: {{ scope.row.name }}</p>
					          <p>Addr: {{ scope.row.address }}</p>
					          <div slot="reference" class="name-wrapper">
					            <el-tag size="medium">{{ scope.row.name }}</el-tag>
					          </div>
					        </el-popover>
					      </template>
					    </el-table-column>
					    <el-table-column
					      label="Operations">
					      <template slot-scope="scope">
					        <el-button
					          size="mini"
					          >Edit</el-button>
					        <el-button
					          size="mini"
					          type="danger"
					          >Delete</el-button>
					      </template>
					    </el-table-column>
					</el-table>
				  </div>
				</el-card>
			</el-row>
		  </el-col>
		  <el-col :xs="24" :sm="24" :md="24" :lg="12" :xl="12">
		  	<el-card class="box-card" style="margin-top: 12px;">
		  		<span style="color: #50649C;font-weight: 500;">Ongoing Projects</span>
		  		<div>
		  			<el-table
					    :data="tableData2"
					    style="width: 100%;font-size: 12px;">
					    <el-table-column
					      label="Project"
					      >
					      <template slot-scope="scope">
					        <i class="el-icon-time"></i>
					        <span style="margin-left: 10px">{{ scope.row.project }}</span>
					      </template>
					    </el-table-column>
					    <el-table-column
					      label="Developer"
					      >
					      <template slot-scope="scope">
					        <el-popover trigger="hover" placement="top">
					          <p>Name: {{ scope.row.name }}</p>
					          <p>Addr: {{ scope.row.address }}</p>
					          <div slot="reference" class="name-wrapper">
					            <el-tag size="medium">{{ scope.row.name }}</el-tag>
					          </div>
					        </el-popover>
					      </template>
					    </el-table-column>
					    <el-table-column
					      label="Operations">
					      <template slot-scope="scope">
					        <el-button
					          size="mini"
					          >Edit</el-button>
					        <el-button
					          size="mini"
					          type="danger"
					          >Delete</el-button>
					      </template>
					    </el-table-column>
					</el-table>
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
            values: [
			      { name: 'Page A', uv: 4000, pv: 2400, amt: 2400 },
			      { name: 'Page B', uv: 3000, pv: 1398, amt: 2210 },
			      { name: 'Page C', uv: 2000, pv: 9800, amt: 2290 },
			      { name: 'Page D', uv: 2780, pv: 3908, amt: 2000 },
			      { name: 'Page E', uv: 1890, pv: 4800, amt: 1700 },
			      { name: 'Page F', uv: 2390, pv: 3800, amt: 2500 },
			      { name: 'Page G', uv: 3490, pv: 4300, amt: 2100 }
			    ],
			values2: [
			      { name: 'A', pv: 400 },
			      { name: 'B', pv: 398 },
			      { name: 'C', pv: 800 },
			      { name: 'D', pv: 908 },
			      { name: 'C', pv: 300 },
			    ],
			tableData: [{
	          date: '2016-05-03',
	          name: 'Tom',
	          address: 'No. 189, Grove St, Los Angeles'
	        }, {
	          date: '2016-05-02',
	          name: 'Tom',
	          address: 'No. 189, Grove St, Los Angeles'
	        }, {
	          date: '2016-05-04',
	          name: 'Tom',
	          address: 'No. 189, Grove St, Los Angeles'
	        }, {
	          date: '2016-05-01',
	          name: 'Tom',
	          address: 'No. 189, Grove St, Los Angeles'
	        }],

	        tableData2: [{
	          project: 'E-Commerce',
	          name: 'Pahi',
	          address: 'No. 189, Guwahati , Assam'
	        }, {
	          project: 'Travel Agency',
	          name: 'Pahi',
	          address: 'No. 189, Guwahati , Assam'
	        }, {
	          project: 'Android App',
	          name: 'Pahi',
	          address: 'No. 189, Guwahati , Assam'
	        }, {
	          project: 'E-Commerce',
	          name: 'Pahi',
	          address: 'No. 189, Guwahati , Assam'
	        }]     
	      }
	    }
	}
</script>