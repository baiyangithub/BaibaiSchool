<template>
    <div class="school">
        <div class="schoolHead">
            <i class="fa fa-angle-left" @click="back"></i>
            <span>选择学校</span>
        </div>
        <search router="school"></search>
        <ul>
            <p class="hotSchool"><i class="fa fa-star"></i>热门学校</p>
            <li v-for="(item, index) of list" :key="index" v-if="item.name.length!=1">
                <i class="fa fa-map-marker"></i>
                <span>{{item.name}}</span>
            </li>
            <p  class="hotSchool" v-else>{{item.name}}</p>
        </ul>
    </div>
</template>

<script>
    import Bus from '../bus.js'
    import search from '../components/search.vue'
    export default {
        name: 'school',
        components: {
            search
        },
        beforeRouteEnter (to, from, next) {
            Bus.$emit('isShow',false)
            next()
        },
        beforeRouteLeave (to, from, next) {
            Bus.$emit('isShow',true)
            next()
        },
        data: () =>{
            return {
                list: [
                    {
                        name: '查看所有学校'
                    },
                    {
                        name: '桂林电子科技大学'
                    },
                    {
                        name: '桂林理工大学'
                    },
                    {
                        name: '广西理工职业技术学院'
                    },
                    {
                        name: '陕西工业职业技术学院                '
                    },
                    {
                        name: '华东交通大学                '
                    },
                    {
                        name: '华侨大学                '
                    },
                    {
                        name: '南华大学                '
                    },
                    {
                        name: '广东岭南职业技术学院                '
                    },
                    {
                        name: 'G'
                    },
                    {
                        name: '桂林电子科技大学'
                    },
                    {
                        name: '桂林电子科技大学'
                    },

                    {
                        name: '桂林电子科技大学'
                    },
                    {
                        name: '桂林电子科技大学'
                    },
                    {
                        name: '桂林电子科技大学'
                    },
                    {
                        name: '桂林电子科技大学'
                    },
                    {
                        name: '桂林电子科技大学'
                    },
                    {
                        name: 'H'
                    },
                    {
                        name: '桂林电子科技大学'
                    },
                    {
                        name: '桂林电子科技大学'
                    },
                    {
                        name: '桂林电子科技大学'
                    },
                    {
                        name: 'N'
                    },
                    {
                        name: '桂林电子科技大学'
                    },
                    {
                        name: '桂林电子科技大学'
                    },
                    {
                        name: '桂林电子科技大学'
                    },
                    {
                        name: '桂林电子科技大学'
                    }
                ]
            }
        },
        methods: {
            back(){
                history.back()
            }
        }
    }
</script>

<style lang="scss" scoped>
    @import '../style/usage/core/reset.scss';
    .schoolHead{
        height: .46rem;
        background: #fff;
        text-align: left;
        line-height: .46rem;
        position: relative;
        font-size: 15px;
        text-align: center;
        i{
            position: absolute;
            font-size: 22px;
            top: .1rem;
            left: .15rem;
        }
    }
    .hotSchool{
        background: #f4f4f4;
        font-size: 15px;
        height: .3rem;
        line-height: .3rem;
        padding-left: .2rem;
        padding-left: .1rem;
    }
    ul{
        position: absolute;
        top: 1.1rem;
        bottom: 0;
        width: 100%;
        overflow-y: scroll;
        background: #fff;
    }
    li{
        font-size: 15px;
        color: #666;
        list-style: none;
        background: #fff;
        padding: .12rem .15rem;
        @include border(1px 0 0 0);
        i{
            margin-right: .1rem;
        }
    }
    li:nth-of-type(1){
        i{
            color: blue;
        }
    }
</style>