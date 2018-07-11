<template>
    <main>
        <router-view></router-view>
        <tabbar v-if="isShow"></tabbar>
    </main>
</template>

<script>

import tabbar from './components/tabbar'
import Bus from './bus.js'

export default {
    name: 'app',
    components: {
        tabbar
    },
    data() {
        return {
            isShow: true
        }
    },
    mounted() {
        Bus.$on('isShow',res =>{
            this.isShow = res
        })
    }
}
</script>


<style lang="scss">
    @import './style/usage/core/reset.scss';
    @import './assets/font-awesome-4.7.0/scss/font-awesome.scss';

    main{
        height: 100%;
        position: relative;
    }
    body{
        background: #f0f0f0;
    }
</style>