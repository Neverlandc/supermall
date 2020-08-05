<template>
    <div class="wrapper" ref="aaaa">
        <ul class="content">
            <li>1</li>
            <li>2</li>
            <li>3</li>
            <li>4</li>
            <li>5</li>
            <li>6</li>
            <li>7</li>
            <li>8</li>
            <li>9</li>
            <li>10</li>
        </ul>
    </div>  
</template>

<script>
    import BScroll from 'better-scroll'

    export default {
        name: 'Category',
        data() {
            return {
                scroll: null
            }
        },
        // 组件创建完后调用
        mounted() {
            this.scroll = new BScroll(document.querySelector('.wrapper'), {
                probeType: 3,
                pullUpload: true
            })

            this.scroll.on('scroll', (position) => {
                console.log(position);
            })

            this.scroll.on('pullingUp', () => {
                console.log('上拉加载更多');
            })
        },
        methods: {
            btnClick() {
                console.log('btnclick');
            }
        }
    }
</script>

<style scoped>

</style>
