<template>
    <div class="tabBar">
        <mt-tabbar v-model="select">
            <mt-tab-item v-for="item of tabMsg" @click.native="handleTabClick(item.path)" :id="item.id" :key="item.id">
                <i slot="icon" :class="item.icon"></i>
                {{item.name}}
            </mt-tab-item>
        </mt-tabbar>
    </div>
</template>

<script>
    export default {
        name: 'tabbar',
        data() {
            return {
                select: 't1',
                tabMsg: [
                    {
                        id: 't1',
                        name: '二手',
                        icon: 'fa fa-envelope',
                        path: '/sale'
                    },
                    {
                        id: 't2',
                        name: '求购',
                        icon: 'fa fa-edit',
                        path: '/buy'
                    },
                    {
                        id: 't3',
                        name: '发布',
                        icon: 'fa fa-plus-square-o',
                        path: '/release'
                    },
                    {
                        id: 't4',
                        name: '我的',
                        icon: 'fa fa-user-o',
                        path: '/user'
                    }
                ]
            }
        },
        methods: {
            handleTabClick(path) {
                this.$router.push({
                    path
                })
            }
        }
    }
</script>

<style lang="scss" scoped>
    @import '../style/usage/core/reset.scss';
    .tabBar{
        background: #fff;
        height: .54rem;
        width: 100%;
        position: absolute;
        bottom: 0;
        .mint-tabbar{
            height: 100%;
            background: #fff;
        }
        .mint-tabbar > .mint-tab-item.is-selected{
            background: #fff;
        }
        .is-selected{
            color: #f5a842 !important;
        }
        a{
            color: #8f8f94;
        }
        .fa{
            font-size: .24rem;
        }
    }
</style>
