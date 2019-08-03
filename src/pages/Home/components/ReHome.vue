<template>
	<div>
		<el-container>
	    <el-header style="text-align: right; font-size: 12px; background-color: deepskyblue;">
	      <el-dropdown>
	        <i class="el-icon-bell" style="margin-right: 15px"></i>
	        <el-dropdown-menu slot="dropdown">
	          <el-dropdown-item>查看</el-dropdown-item>
	          <el-dropdown-item>新增</el-dropdown-item>
	          <el-dropdown-item>删除</el-dropdown-item>
	        </el-dropdown-menu>
	      </el-dropdown>
	      <span style="float: left; font-size: 24px; color: #FFFFFF;">微人事</span>
	      <span style="color: #FFFFFF; float: right; margin-right: 60px; ">系统管理员</span>
	        <div style="float: right; margin-right: -120px; margin-top: 10px;">
		      <el-avatar icon="el-icon-user-solid"></el-avatar>
		    </div>
	    </el-header>
	  </el-container>
    <el-container style="float: left ;height: 500px; width: 200px; border: 1px solid #eee">
	  <el-aside width="200px" style="height: 648px;background-color: rgb(238, 241, 246)">
	    <el-menu :default-openeds="['1', '3']">
	    	
	      <el-submenu index="9">
	        <template slot="title"><i class="el-icon-user-solid"></i>员工资料</template>
	        <el-menu-item-group>
	          <el-menu-item index="1-1">基本资料</el-menu-item>
	        </el-menu-item-group>
	      </el-submenu>
	      
	      <el-submenu index="2">
	        <template slot="title"><i class="el-icon-bank-card"></i>人事管理</template>
	        <el-menu-item-group>
	          <el-menu-item index="1-1">员工奖惩</el-menu-item>
	          <el-menu-item index="1-2">员工培训</el-menu-item>
	          <el-menu-item index="1-2">员工调薪</el-menu-item>
	          <el-menu-item index="1-2">员工调动</el-menu-item>
	        </el-menu-item-group>	          
	      </el-submenu>
	      
	      <el-submenu index="7">
	        <template slot="title"><i class="el-icon-chat-line-square"></i>薪资管理</template>
	        <el-menu-item-group>
	          <el-menu-item index="1-1">工资账套管理</el-menu-item>
	          <el-menu-item index="1-2">员工账套设置</el-menu-item>
	          <el-menu-item index="1-2">工资表管理</el-menu-item>
	          <el-menu-item index="1-2">月末处理</el-menu-item>
	          <el-menu-item index="1-2">工资表查询</el-menu-item>
	        </el-menu-item-group>
	      </el-submenu>
	      
	      <el-submenu index="4">
	        <template slot="title"><i class="el-icon-s-data"></i>统计管理</template>
	        <el-menu-item-group>
	          <el-menu-item index="2-1">综合信息管理</el-menu-item>
	          <el-menu-item index="2-2">员工积分管理</el-menu-item>
	          <el-menu-item index="2-2">认识信息管理</el-menu-item>
	          <el-menu-item index="2-2">认识记录管理</el-menu-item>
	        </el-menu-item-group>
	      </el-submenu>
	      
	      <el-submenu index="5">
	        <template slot="title"><i class="el-icon-setting"></i>系统管理</template>
	        <el-menu-item-group>
	          <el-menu-item index="3-1">基础信息设置</el-menu-item>
	          <el-menu-item index="3-2">系统管理</el-menu-item>
	          <el-menu-item index="3-1">操作日志管理</el-menu-item>
	          <el-menu-item index="3-2">操作员管理</el-menu-item>
	          <el-menu-item index="3-1">备份恢复数据库</el-menu-item>
	          <el-menu-item index="3-2">初始化数据库</el-menu-item>
	        </el-menu-item-group>
	      </el-submenu>
	    </el-menu>
	  </el-aside>
	</el-container>
				
	<el-container style="float: right; height: 649px; width: 1132px;">
		<el-breadcrumb style="margin-left: 20px; margin-top: 20px;"  separator="/">
		  <el-breadcrumb-item :to="{ path: 'Home' }">首页</el-breadcrumb-item>
		  <el-breadcrumb-item><a href="/">主页</a></el-breadcrumb-item>
		</el-breadcrumb>
	</el-container>
	
	</div>
</template>

<script>
</script>


<style scoped>
	 .el-header {
	    background-color: #B3C0D1;
	    color: #333;
	    line-height: 60px;
	  }
	  
	  .el-aside {
	    color: #333;
	  }
</style>
