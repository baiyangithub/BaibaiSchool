<template>
    <div class="head">
        <div>
            <i class="fa  fa-angle-left" @click="handleClick"></i>
        </div>
        <div>
            <span>{{title}}</span>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'myheade',
        props: ["title"],
        methods:{
            handleClick(){
                this.$router.push("/user")
            }
        }
    }
</script>

<style  lang="scss" scoped>
    @import '../style/usage/core/reset.scss';
    .head{
        position: relative;
        @include flexbox();
        @include flex-direction(row);
        height: .45rem;
        background: #fff;
        font-size: .16rem;
        div:first-child{
            i{
                font-size: .3rem;
                margin-left: 15px;
                line-height: .45rem;
                // color: #c3c3c3;
            }
        }
        div:last-child{
            @include flex(3);
            text-align: center;
            line-height: .45rem;
            span{
                color: #666;
                font-size: .15rem;
            }
        }
    }
</style>