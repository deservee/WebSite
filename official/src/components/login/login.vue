<template>
  <!--flex弹性盒子模型，justify-content：主抽 -->
  <div style="display: flex;justify-content: center;margin-top: 150px">
    <el-card style="width: 400px">
      <div slot="header" class="clearfix">
        <span>登录</span>
        <!-- <span>{{headerTitle}}</span> -->
      </div>
      <div class="kuang">
        <el-from>
          <el-from-item lable prop="username">
            <el-input v-model="username" placeholder="请输入账号" type="text"></el-input>
            <!-- <el-input v-model="logoData.username" placeholder="请输入账号" type="text"></el-input> -->
          </el-from-item>
          <el-from-item lable prop="password">
            <el-input
              v-model="password"
              placeholder="请输入密码"
              style=" margin-top: 5px"
              type="password"
            ></el-input>
            <!-- <el-input v-model="logoData.passwd" placeholder="请输入密码" style=" margin-top: 5px" type="password"></el-input> -->
          </el-from-item>
          <el-button
            :type="primary"
            style="width: 100%; margin-top: 5px"
            @click="login"
            :loading="loading"
            :style="buttonStyle"
          >登 录</el-button>
          <el-alert v-if="showMsg" :title="msg" :type="msgType" show-icon></el-alert>
          <slot name="default"></slot>
        </el-from>
      </div>
    </el-card>
  </div>
</template>

<script>
    import shal from 'js-sha1'
    import Cookies from 'js-cookie'

export default {
    //单页面中不支持前面的data:{}方式
    name: "login",
    data() {
      //相当于以前的function data(){},这是es5之前的写法，新版本可以省略掉function
      return{
          loading: false,
                showMsg: false,
                msg: '',
                msgType: 'success',
                logoData: {
                    username: "",
                    passwd: ""
                },
        //之前是在里面直接写username，password等等，但是这里要写return
        //因为一个组件不管要不要被其他组件用，只要这样定义了，它就会认为可能这个组件会在其他的组件中使用
        //比如说在这里定义了一个变量，然后把这个组件引入到A组件中，A组件中修改了这个变量
        //同时这个组件也在B组件中引用了，这时候A里面一修改，B里面也变了，它们用的是一个值
        //可是一般来说可能希望在不同的组件中引用的时候，使用不同的值，所以这里要用return
        //这样在A组件和B组件分别引用这个变量的时候是不会互相影响的
        // user:{
        //   username:'zhangsan',
        //   password:'123',
          //为了登录方便，可以直接在这里写好用户名和密码的值
                 loading: false,
                showMsg: false,
                msg: '',
                msgType: 'success',
                logoData: {
                    username: "",
                    passwd: ""
                },
                rules: {
                    username: [
                        {required: true, message: '请输入账号，格式为邮箱地址', trigger: 'blur'},
                        {type: 'email', message: '请输入正确的账号，格式为邮箱地址', trigger: ['blur', 'change']}
                    ],
                    passwd: [
                        {required: true, message: '请输入密码', trigger: 'blur'},
                        {min: 6, max: 32, message: '密码长度在 6 到 32 个字符', trigger: ['blur', 'change']}
                    ]
                }
            }
        },
        props: {
            buttonStyle: {
                type: Object,
                default: function () {
                    return {
                        'height': '50px',
                        'border-radius': '0px',
                        '-moz-box-shadow': '0px 2px 5px #999',
                        '-webkit-box-shadow': '0px 2px 5px #999',
                        'box-shadow': '0px 2px 5px #999',
                        'font-size': '22px'
                    }
                }
            },
            primary: {
                type: String,
                default: "primary"
            },
            width: {
                default: '360px'
            },
            url: {
                type: String,
                default: 'Admin/account/login'
            },
            go: {
                type: String,
                default: 'home'
            },
            success: {
                type: Function || null
            },
            error: {
                type: Function || null
            },
            headerTitle: {
                type: String
            }
        },
        computed: {
            style() {
                return {
                    border: 'none',
                    borderRadius: 0,
                    width: this.width
                }
            }
        },
        methods:{
           login(){//一点击登录按钮，这个方法就会执行
           alert(JSON.stringify(this.user))//可以直接把this.user对象传给后端进行校验用户名和密码
           }
        }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.kuang .el-input__inner {
  height: 50px;
  line-height: 50px;
  border-radius: 0px;
}
</style>