<template>
    <div id="app">
      <el-container>
            
            <!-- 侧边栏 -->
        <el-aside width="200px" >
            <div class="logo">万锋智慧</div>
           
        <el-menu default-active="1-4-1" class="el-menu-vertical-demo" @open="handleOpen" @close="handleClose" :collapse="isCollapse">
         <el-menu-item index="1">
            <i class="el-icon-s-home"></i>
            <span slot="title">管理首页</span>
        </el-menu-item>    
        <el-submenu index="2">
            <template slot="title">
            <i class="el-icon-user"></i>
            <span slot="title">学员管理</span>
            </template>
            <el-menu-item-group>
            
            <el-menu-item index="1-1">学员项目管理</el-menu-item>
            <el-menu-item index="1-2">学员资料</el-menu-item>
            <el-menu-item index="1-3">学员宿舍</el-menu-item>          
            </el-menu-item-group>                                  
        </el-submenu>
        <el-menu-item index="3">
            <i class="el-icon-edit"></i>
            <span slot="title">考勤管理</span>
        </el-menu-item>
        <el-menu-item index="4" >
            <i class="el-icon-document"></i>
            <span slot="title">数据统计</span>
        </el-menu-item>
        <el-menu-item index="5">
            <i class="el-icon-chat-dot-round"></i>
            <span slot="title">我的中心</span>
        </el-menu-item>
        </el-menu>
                </el-aside>
          <el-container>
                <!-- 顶部 -->
            <el-header><el-row type="flex" class="row-bg" justify="space-between">
            <el-col :span="6"><div class="grid-content bg-green"><i class="el-icon-s-fold" ></i></div></el-col>
            <el-col :span="6"><div class="grid-content bg-green">千锋管理系统</div></el-col>
            <el-col :span="6"><div class="grid-content bg-green">欢迎您：管理员  退出</div></el-col>
            </el-row>
            </el-header>
            <!-- 主体部分 -->
            <el-main>Main</el-main>
          </el-container>
      </el-container>
    </div>
</template>

<style>
  .el-header, .el-footer {
    background-color: #B3C0D1;
    color: #333;
    text-align: center;
    line-height: 60px;
  }
  
  .el-aside {
    background-color: #D3DCE6;
    color: #333;
    text-align: center;
    line-height: 200px;
  }
  
  .el-main {
    background-color: #E9EEF3;
    color: #333;
    text-align: center;
    line-height: 160px;
  }
  
  body > .el-container {
    margin-bottom: 40px;
  }
  
  .el-container:nth-child(5) .el-aside,
  .el-container:nth-child(6) .el-aside {
    line-height: 260px;
  }
  
  .el-container:nth-child(7) .el-aside {
    line-height: 320px;
  }
    /* 侧边栏样式 */
  .el-menu-vertical-demo:not(.el-menu--collapse) {
    width: 200px;
    min-height: 400px;
  }

  /* 顶部样式 */
  .el-row {
    margin-bottom: 20px;
    
  }
  .el-col {
    border-radius: 4px;
  }
  .bg-purple-dark {
    background: #99a9bf;
  }
  .bg-purple {
    background: #d3dce6;
  }
  .bg-purple-light {
    background: #e5e9f2;
  }
  .grid-content {
    border-radius: 4px;
    min-height: 36px;
  }
  .row-bg {
    padding: 10px 0;
    background-color: #f9fafc;
    
  }
.logo{
    height: 60px;
    background: linear-gradient(135deg,#4c67ff,#5635df);
    background-image: url('../../imgs/../imgs/logo.png');
    background-size: 80%;
    background-repeat: no-repeat;
    background-position: 50%;
    
}



.el-aside {
    background: linear-gradient(135deg,#4c67ff,#5635df);
}

.el-row {
    margin: 0;
    padding: 0;
    background: linear-gradient(135deg,#4c67ff,#5635df);
    color: #fff;
    
    
}
.el-icon-s-fold {
    font-size: 30px;
    cursor: pointer;
    color: #fff;
    text-align: left;
        text-align: left;
        
    
   
    
   
}




  
</style>

<script>
  export default {
    data() {
      return {
        isCollapse: false
      };
    },
    methods: {
      handleOpen(key, keyPath) {
        console.log(key, keyPath);
      },
      handleClose(key, keyPath) {
        console.log(key, keyPath);
      }
    }
  }
</script>