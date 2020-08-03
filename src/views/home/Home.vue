<template>
    <div id="home">
        <nav-bar class="home-nav"><div slot="center">购物街</div></nav-bar>
        <home-swiper :banners="banners"/>
    </div>    
</template>

<script>
    import NavBar from 'components/common/navbar/NavBar'
    import HomeSwiper from './childComps/HomeSwiper'

    import {getHomeMultidata} from 'network/home'
    

    export default {
        name: 'Home',
        components: {
            NavBar,
            HomeSwiper
        },
        data() {
            return {
                banners: [],
                dKeywords: [],
                keywords: [],
                recommends: []
            }
        },
        created() {
            // 1.请求多个数据
            getHomeMultidata().then(res => {
                // console.log(res)
                this.banners = res.data.banner.list;
                this.dKeywords = res.data.dKeyword.list;
                this.keywords = res.data.keywords.list;
                this.recommends = res.data.recommend.list;
            })
        }
    }
</script>

<style>
    .home-nav {
        background-color: var(--color-tint);
        color: #fff;
    }
</style>
