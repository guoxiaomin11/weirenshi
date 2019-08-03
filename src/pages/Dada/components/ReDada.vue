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
				
	<el-container style="float: right; height: 650px; width: 1132px;">
		<el-breadcrumb style="margin-left: 20px; margin-top: 20px;"  separator="/">
		  <el-breadcrumb-item :to="{ path: 'Home' }">首页</el-breadcrumb-item>
		  <el-breadcrumb-item><a href="/">主页</a></el-breadcrumb-item>
		</el-breadcrumb>
		
		<el-input placeholder="请输入内容" v-model="input" :disabled="true" 
			style="width: 280px; height: 30px; margin-top: 50px; margin-left: -80px;">
		</el-input>
		<el-button style="float: left; margin-left: 8px; margin-top: 50px; height: 40px;" 
  				type="primary" icon="el-icon-circle-plus">搜索</el-button>
  		<el-button style="float: left; margin-left: 8px; margin-top: 50px; height: 40px;" 
  				type="primary" icon="el-icon-circle-plus">高级搜索</el-button>
  		<div style="width: 220px; height: 40px; float: left; margin-left: 310px; margin-top: 50px;">
  			<el-button style="float: left; width: 100px; margin-left: -30px;" icon="el-icon-upload2"
  				 type="primary">导入数据</el-button>
  			<el-button icon="el-icon-download" style="width: 100px;" type="success">导出数据</el-button>
  			<el-button style="float: left; width: 100px; margin-left: 190px; margin-top: -40px;" 
  				type="primary" icon="el-icon-circle-plus">添加员工</el-button>
  		</div>
  		
  		<el-table
		    :data="tableData"
		    border
		    style="width: 100%; float: left; margin-left: -1040px; height: 409px; margin-top: 110px;">
		    <el-table-column
		      fixed
		      prop="date"
			  type="selection"
		      width="30"
		      height="37">
		    </el-table-column>
		    <el-table-column
		      fixed
		      prop="name"
		      label="姓名"
		      width="90">
		    </el-table-column>
		    <el-table-column
		      prop="province"
		      label="工号"
		      width="85">
		    </el-table-column>
		    <el-table-column
		      prop="city"
		      label="性别"
		      width="50">
		    </el-table-column>
		    <el-table-column
		      prop="address"
		      label="出生日期"
		      width="100">
		    </el-table-column>
		    <el-table-column
		      prop="card"
		      label="身份证号码"
		      width="180">
		    </el-table-column>
		    <el-table-column
		      prop="Wedding"
		      label="婚烟状态"
		      width="100">
		    </el-table-column>
		    <el-table-column
		      prop="Famous"
		      label="民族"
		      width="100">
		    </el-table-column>
		    <el-table-column
		      prop="citya"
		      label="籍贯"
		      width="100">
		    </el-table-column>
		    <el-table-column
		      prop="political"
		      label="政治面貌"
		      width="100">
		    </el-table-column>
		    <el-table-column
		      prop="mail"
		      label="电子邮箱"
		      width="200">
		    </el-table-column>
		    <el-table-column
		      prop="telephone"
		      label="电话号码"
		      width="120">
		    </el-table-column>
		    <el-table-column
		      prop="contact"
		      label="联系地址"
		      width="200">
		    </el-table-column>
		    <el-table-column
		      prop="department"
		      label="所属部门"
		      width="100">
		    </el-table-column>
		    <el-table-column
		      prop="positiona"
		      label="职位"
		      width="100">
		    </el-table-column>
		    <el-table-column
		      prop="jobtitle"
		      label="职称"
		      width="100">
		    </el-table-column>
		    <el-table-column
		      prop="Dateentry"
		      label="入职日期"
		      width="110">
		    </el-table-column>
		     <el-table-column
		      prop="Resignationdata"
		      label="辞职日期"
		      width="110">
		    </el-table-column>
		    <el-table-column
		      prop="Contractdata"
		      label="合同日期"
		      width="110">
		    </el-table-column>
		    <el-table-column
		      prop="highesteducation"
		      label="最高学历"
		      width="110">
		    </el-table-column>
		    <el-table-column
		      fixed="right"
		      label="操作"
		      width="100">
		      <template slot-scope="scope">
		        <el-button @click="handleClick(scope.row)" type="text" size="small">查看</el-button>
		        <el-button type="text" size="small">编辑</el-button>
		      </template>
		    </el-table-column>
		  </el-table>	
	</el-container>
	<el-pagination
		style="float: right; margin-top: -130px; margin-right: -8px;"
		background
		layout="prev, pager, next"
		:total="1000">
	</el-pagination>
	<el-button style="float: left; margin-left: 220px; margin-top: -128px;  "  type="warning" disabled>批量删除</el-button>
	</div>
</template>

<script>
	export default {
	  data () {
	      return {
	          isShow: false,
	          btnText: "隐藏",
	      }
       },
	   methods:{
            showToggle(){
                this.isShow = !this.isShow
                if(this.isShow){
                    this.btnText = "隐藏"
                }else{
                    this.btnText = "显示"
                }
            }
        }
	}	
</script>
<script>
  export default {
    methods: {
      handleClick(row) {
        console.log(row);
      }
    },

    data() {
      return {
        tableData: [{
          date: '2016-05-02',
          name: '一点雨',
          province: '01',
          city: '男',
          address: '1990-01-01',
          card:610122199001011256,
          Wedding:'已婚',
          Famous:'汉族',
          citya:'湖南岳阳',          
		  political:'公民',
          mail:'1256582713@qq.com',
          telephone:'18565558897',
          contact:'深圳市南山区',
          department:'总办',
          positiona:'技术总监',
          jobtitle:'教授',
          Dateentry:'2018-01-01',
          Resignationdata:'2018-01-02',
          Contractdata:'3.5年',
          highesteducation:'博士'
        }, {
          date: '2016-05-04',
          name: '陈静',
          province: '02',
          city: '男',
          address: '1990-01-01',
          card:610122199001011256,
          Wedding:'已婚',
          Famous:'汉族',
          citya:'湖南岳阳',          
		  political:'公民',
          mail:'1256582713@qq.com',
          telephone:'18565558897',
          contact:'深圳市南山区',
          department:'总办',
          positiona:'技术总监',
          jobtitle:'教授',
          Dateentry:'2018-01-01',
          Resignationdata:'2018-01-02',
          Contractdata:'3.5年',
          highesteducation:'博士'
        }, {
          date: '2016-05-01',
          name: '赵琳浩',
          province: '03',
          city: '男',
          address: '1990-01-01',
          card:610122199001011256,
          Wedding:'已婚',
          Famous:'汉族',
          citya:'湖南岳阳',          
		  political:'公民',
          mail:'1256582713@qq.com',
          telephone:'18565558897',
          contact:'深圳市南山区',
          department:'总办',
          positiona:'技术总监',
          jobtitle:'教授',
          Dateentry:'2018-01-01',
          Resignationdata:'2018-01-02',
          Contractdata:'3.5年',
          highesteducation:'博士'
        }, {
          date: '2016-05-03',
          name: '鹿存亮',
          province: '04',
          city: '男',
          address: '1990-01-01',
          card:610122199001011256,
          Wedding:'已婚',
          Famous:'汉族',
          citya:'湖南岳阳',          
		  political:'公民',
          mail:'1256582713@qq.com',
          telephone:'18565558897',
          contact:'深圳市南山区',
          department:'总办',
          positiona:'技术总监',
          jobtitle:'教授',
          Dateentry:'2018-01-01',
          Resignationdata:'2018-01-02',
          Contractdata:'3.5年',
          highesteducation:'博士'
        }, {
          date: '2016-05-01',
          name: '王小虎',
          province: '05',
          city: '男',
          address: '1990-01-01',
          card:610122199001011256,
          Wedding:'已婚',
          Famous:'汉族',
          citya:'湖南岳阳',          
		  political:'公民',
          mail:'1256582713@qq.com',
          telephone:'18565558897',
          contact:'深圳市南山区',
          department:'总办',
          positiona:'技术总监',
          jobtitle:'教授',
          Dateentry:'2018-01-01',
          Resignationdata:'2018-01-02',
          Contractdata:'3.5年',
          highesteducation:'博士'
        }, {
          date: '2016-05-01',
          name: '王小虎',
          province: '05',
          city: '男',
          address: '1990-01-01',
          card:610122199001011256,
          Wedding:'已婚',
          Famous:'汉族',
          citya:'湖南岳阳',          
		  political:'公民',
          mail:'1256582713@qq.com',
          telephone:'18565558897',
          contact:'深圳市南山区',
          department:'总办',
          positiona:'技术总监',
          jobtitle:'教授',
          Dateentry:'2018-01-01',
          Resignationdata:'2018-01-02',
          Contractdata:'3.5年',
          highesteducation:'博士'
        }]
      }
    }
  }
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
