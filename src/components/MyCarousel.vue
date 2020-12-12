<template>
    <a-carousel autoplay>
        <div><img src="../assets/img/srfsx.jpg" alt="蒜蓉粉丝虾"/></div>
        <div><img src="../assets/img/hlbnr.jpg" alt="炖牛肉"/></div>
        <div><img src="../assets/img/tcpg.jpg" alt="糖醋排骨"/></div>
        <div><img src="../assets/img/hgr.jpg" alt="回锅肉"/></div>
    </a-carousel>
</template>
<script>
    export default {
        name: 'MyCarousel'
    }
</script>
<style scoped>
    /* For demo */
    .ant-carousel >>> .slick-slide {
        text-align: center;
        margin:0 auto;
        height: 500px;
        overflow: hidden;
    }

    .ant-carousel .slick-slide img{
        display: unset;
    }
</style>