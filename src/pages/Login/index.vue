
<template>
  <div class="login-page">                    
    <div class="background-input">
      <div class="content">
           <h1 data-v-5ea9a656="" class="title">千锋管理系统</h1>
          <el-form :model="loginForm" status-icon :rules="rules" ref="loginForm" label-width="100px" class="demo-loginForm">
          <el-form-item label="用户名" prop="username" >
            <el-input type="text" v-model="loginForm.username" autocomplete="off"></el-input>
          </el-form-item>
          <el-form-item label="密码" prop="password">
            <el-input type="password" v-model="loginForm.password" autocomplete="off"></el-input>
          </el-form-item>
        
          <el-form-item>
            <el-button type="primary" @click="submitForm('loginForm')">提交</el-button>
          </el-form-item>
          </el-form> 
      </div>
        
    </div>
 
      <video data-v-5ea9a656="" muted="muted" src="../../video/bg_video.d2d602a9.mp4" autoplay="autoplay" loop="loop" preload="auto" class="bg_video"></video>

  </div>
</template>
  
<script>
  export default {
    data() {
      var checkAge = (rule, value, callback) => {
        if (!value) {
          return callback(new Error('年龄不能为空'));
        }
        setTimeout(() => {
          if (!Number.isInteger(value)) {
            callback(new Error('请输入数字值'));
          } else {
            if (value < 18) {
              callback(new Error('必须年满18岁'));
            } else {
              callback();
            }
          }
        }, 1000);
      };
      var vaiidateUsername = (rule, value, callback) => {
          if (!value) {
            callback("4到16位(字母，数字，下划线)")
          }else {
            callback()
          }
      };
      var validatePassword = (rule, value, callback) => {
        if (!value) {
            callback("请输入密码")
          }else {
            callback()
          }
      };
      return {
        loginForm: {
          username: '',
          password: ''
         
        },
        rules: {
          username: [
            { validator: vaiidateUsername, trigger: 'blur' }
          ],
          password: [
            { validator: validatePassword, trigger: 'blur' }
          ]
        }
      };
    },
    methods: {
      submitForm(formName) {
        this.$refs[formName].validate((valid) => {
          if (valid) {
            alert('submit!');
          } else {
            console.log('error submit!!');
            return false;
          }
        });
      },
      resetForm(formName) {
        this.$refs[formName].resetFields();
      }
    }
  }
</script>

<style>

/*表单样式*/ 
.el-form {
  width: 400px;
}

.el-from-item {
    text-align: right;
    vertical-align: middle;
    float: left;
    font-size: 14px;   
    line-height: 40px;
    padding: 0 12px 0 0;
    box-sizing: border-box;
    margin:auto
    
}

.el-input {
    position: absolute;
    right: 25px;
    width: 250px;
    transition: all .5s;
    height: 40px;
    line-height: 100%;
    overflow: hidden;
    color: #fff;
    border: .04761905rem solid #fff;   
}

.login-page .background-input {
 position: relative;
    z-index: 9;
    width: 25rem;
    height: 30.47619048rem;
    position: absolute;
    top: 50%;
    left: 75%;
    transform: translate(-50%,-50%);
    border-radius: 11px;
    background: rgba(83,107,182,.46);
    background: rgba(0,0,0,.2);
    text-align: center;
 }

 .background-input .title {
    color: #fff;
    margin-bottom: 50px;
    
   
 }

 .login-page .background-input .content {
   margin-top: 100px;
 }

 .login-page .background-input .content .el-button {
   
   width: 250px;
   margin-right: 100px;  
 }

.bg_video {
    object-fit: contain;
}

.login-page .background-input .content .el-button{
      
  background: linear-gradient(90deg,#1596fb,#002dff);
}


</style>
