<template>
    <div>
        <myhead :title="'注册'"></myhead>
        <div class="login">
            <div class="main">
                <div class="reg">

                    <div class="item " v-for="item of userMsg" :key="item.id">
                        <label>{{item.name}}&nbsp;&nbsp;|</label>
                        <input type="text" :placeholder="item.placeholder">
                    </div>

                    <div><input class="checked" type="checkbox" checked="checked"><a>我同意</a>&nbsp;&nbsp;<a id="agree"><i class="fa  fa-angle-left"></i> <i class="fa  fa-angle-left"></i>&nbsp;&nbsp;柚子校园用户协议&nbsp;&nbsp;<i class="fa  fa-angle-right"></i><i class="fa  fa-angle-right"></i> </a></div>
                    <div><input class="checked" type="checkbox" checked="checked"><a>记住我的登录状态</a></div>
                    

                    <div class="Button">登&nbsp;录</div>

                    <div class="other">
                        <a>忘记密码</a>&nbsp;
                        |&nbsp;&nbsp;
                        <a @click="handleClick">立即注册</a>
                    </div>

                </div>
            </div>
        </div>
    </div>
</template>

<script>
import myhead from "../components/Userheader"
    export default {
        name:"login",
        components:{
            myhead
        },
        data(){
            return{
                userMsg:[
                    {
                        id:"U1",
                        name:"账号",
                        placeholder:"请输入用户名"
                    },
                    {
                        id:"U2",
                        name:"密码",
                        placeholder:"请输入密码"
                    },
                    {
                        id:"U3",
                        name:"邮箱",
                        placeholder:"请输入邮箱"
                    },
                    {
                        id:"U4",
                        name:"学校",
                        placeholder:"请输入学校"
                    }
                ]
            }
        },
        methods: {
            handleClick(){
                this.$router.push("/user/register")
            }
        }
    }
</script>

<style lang="scss" scoped>
@import "../../src/style/usage/core/reset";
    .login{
        background: #f0f0ff;
        .main{
            height: 2.74rem;
            // background: red;
            @include flexbox();
            @include justify-content();
            #agree{
                    color: #66CC99;
                }
            .reg{
                width: 3.55rem;
                height: 1.45rem;
                margin-top: .1rem;
                .item{
                    @include flexbox();
                    @include align-content();
                    width: 100%;
                    height: .5rem;
                    background: #fff;
                    margin-top: 10px;
                    padding-left: .1rem;
                    label{
                        color: #555;
                        display: inline-block;
                        font-size: .16rem;
                        width: .46rem;
                        height: 100%;
                        line-height: .5rem;
                        text-align: center;
                    }
                    input{
                        width: 2.24rem;
                        border: none;
                        margin-left: 10px;
                        
                    }
                }
                .checked{
                    margin-top: 10px;
                }
                a{
                    color: #555;
                    font-size: .16rem;
                }
                .Button{
                    @include flexbox();
                    @include align();
                    width: 3.55rem;
                    height: .46rem;
                    background: #aaa;
                    color: #fff;
                    font-size: .16rem;
                    border-radius: .03rem;
                    margin-top: .15rem;
                }
                .other{
                    @include flexbox();
                    @include align();
                    margin-top: .1rem;
                }
            }
        }
    }

</style>