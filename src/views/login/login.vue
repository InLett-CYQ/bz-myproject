<template>
  <div class='login-container'>
      <div class="bb">
        <el-form status-icon  ref="ruleForm" label-width="100px"  class="login-form">
            <el-form-item>
                <div class="title-container">微气象监测系统</div>
            </el-form-item>
            <el-form-item label="" prop="user">
                <el-input type="text"  autocomplete="off"  label="" prefix-icon="iconfont iconuser" placeholder="账户"></el-input>
            </el-form-item>
            <el-form-item label="" prop="pass">
                <el-input type="password"  autocomplete="off" prefix-icon="iconfont iconlock" placeholder="密码"></el-input>
            </el-form-item>
            <el-form-item label="" prop="code">
                <el-input type="text" placeholder="验证码" prefix-icon="iconfont iconcode"></el-input>
                <span class="validateCode">X7Pu</span>
                <span  class="forgetpwd" @click="dialogVisible = true">忘记密码?</span>
            </el-form-item>
            <el-form-item>
                <el-button type="primary" round>登录</el-button>
            </el-form-item>
        </el-form>
      </div>
    <el-dialog
        title="忘记密码"
        :visible.sync="dialogVisible"
        width="25%"
        :before-close="handleClose">
        <i class="iconfont iconsuccess"></i>
        <span>联系信息</span>
        <br><br><br>
        <p>电 话: 029-84215660   /   18629380830（郑经理）</p><br>
        <p>传 真: 029-81337221</p>
        <span slot="footer" class="dialog-footer">
            <el-button type="primary" @click="dialogVisible = false">关  闭</el-button>
        </span>
    </el-dialog>
  </div>
</template>

<script>
export default {
  name: '',
  data () {
    return {
      dialogVisible: false
    }
  },
  created () {},
  methods: {
    open () {

    }
  }
}
</script>

<style lang="scss" >
    $bg: #283443;
    $light_gray:#fff;
    $cursor: #fff;
    .login-container{
        min-height: 100%;
        width: 100%;
        // background-color: $bg;
        background: url('../../assets/bg-min.png') no-repeat center center;
        background-size: 100% 100%;
        overflow: hidden;
        .login-form {
            width: 520px;
            max-width: 100%;
            position: absolute;
            left: 0;
            top: 20px;
            .title-container{
                   font-family: '微软雅黑';
                   color:#fff;
                   font-size: 40px;
                   margin: 30px auto;
                   text-align: center;
                   letter-spacing: 10px;
            }
            .el-input__prefix{
                width: 20px !important;
                height: 20px !important;
            }
             input {
                background: transparent;
                border: 0px;
                border-bottom: 1px  solid #66b1ff;
                font-size: 18px;
                // -webkit-appearance: none;
                // border-radius: 0px;
                padding: 12px 5px 12px 50px;
                color: $light_gray;
                height: 47px;
                caret-color: $cursor;
                &:-webkit-autofill {
                    box-shadow: 0 0 0px 1000px $bg inset !important;
                    -webkit-text-fill-color: $cursor !important;
                }
            }
            .iconfont{
                font-size: 30px;
                color: #fff;
            }
            .el-form-item::after, .el-form-item::before{
                display: none !important;
                content: ''!important;
            }
            .validateCode{
                display: inline-block;
                width: 100px;
                text-align: center;
                position: absolute;
                color: #fff;
                right: 0px;
                font-size: 20px;
                letter-spacing: 10px;
                cursor: pointer;
                background-color: rgba($bg, $alpha: 0.8);
            }
            .forgetpwd{
                font-size: 18px;
                position: absolute;
                right: 0;
                top: 100px;
                cursor: pointer;
                margin-top: 10px;
                text-decoration: underline;
                z-index: 2;
            }
        }
        .login-form .el-button{
            width: 60%;
            margin-left: 80px;
            margin-top: 30px;
            background-color: rgba($bg, $alpha: 0) !important;
            font-size: 18px;
        }
       .login-form .el-button:hover{
            background-color: rgba($bg, $alpha: 0);
            box-shadow: 0px 0px 10px yellow;

        }
    }
</style>

<style lang="scss" scope>
    $colorfont:#66b1ff;
    $bg: #283443;
    /*定义两个伪类元素的位置*/
    .bb, .bb::before, .bb::after {
        position: absolute;
        top: 0;
        bottom: 0;
        left: 0;
        right: 0;
    }
    /*定义容器bb的样式及边框的样式*/
    .bb {
        width: 600px;
        height: 500px;
        background: no-repeat 50%/70% rgba(0, 0, 0, 0.1);
        color: #0d9ad1c7;
        position: absolute;
        left: 60%;
        top: 50%;
        transform: translate(0,-50%);
    }
    /*定义两个伪类的样式及动画开始*/
    .bb::before, .bb::after {
        content: '';
        z-index: 1;
        margin: -5%;
        box-shadow: inset 0 0 0 1px;
        animation: clipMe 8s linear infinite;
    }
    /*前一个伪类的动画提前4s执行*/
    .bb::before {
        animation-delay: -4s;
    }
    /*定义帧动画*/
    @keyframes clipMe {
        0%,100%{
            clip: rect(0px, 620.0px, 2px, 0px);
        }
        25% {
            clip: rect(0px, 2px, 520.0px, 0px);
        }
        50% {
            clip: rect(518.0px, 620.0px, 520.0px, 0px);
        }
        75% {
            clip: rect(0px, 620.0px, 520.0px, 618.0px);
        }
    }
    .el-dialog__title{
        font-size: 24px !important;
        color: #66b1ff !important;
    }
    .el-dialog__header{
        // background-color: ghostwhite;
        border-bottom: 2px solid gainsboro;
    }
    .el-dialog__body  p{
        letter-spacing: 2px;
        font-size: 18px;
        text-indent: 50px;
        color: #66b1ff;
    }
    .el-dialog__body span{
        font-size: 20px;
        color: #66b1ff;
    }
    .dialog-footer .el-button{
        width: 100px;
        font-size: 18px;
        background-color: rgba($bg, $alpha: 0);
    }
    .dialog-footer .el-button:hover{
        background-color: rgba($colorfont, $alpha: 0.4);
    }
   .el-dialog__body .iconfont{
        font-size: 24px;
        padding: 5px 10px;
        color: rgb(12, 82, 72);
    }
    .el-dialog{
        margin: 0px !important;
        position: absolute !important;
        left: 50% !important;
        top: 50% !important;
        height: 28% !important;
        transform: translate(-50%,-50%) !important;
        background-color: rgba(0, 0, 0, 0.2) !important;
    }

</style>
