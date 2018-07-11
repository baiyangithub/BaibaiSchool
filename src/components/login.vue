<template>
    <div>
        <myhead :title="'登录'"></myhead>
        <div class="login">
            <div class="main">
                <div class="reg">

                    <div class="item " v-for="item of userMsg" :key="item.id">
                        <label>{{item.name}}&nbsp;&nbsp;|</label>
                        <input type="text" :placeholder="item.placeholder">
                    </div>
                    
                    <input class="checked" type="checkbox" checked="checked"><a>记住我的登录状态</a>

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
                        placeholder:"请输入用户名/邮箱"
                    },
                    {
                        id:"U2",
                        name:"密码",
                        placeholder:"请输入密码"
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