<template>
<div class="wrapper">
  <swiper :options="swiperOption">
    <!-- slides -->
    <swiper-slide v-for="item of swiperList" :key="item.id">
      <img :src='item.imgUrl'
           class="swiper-img"
           alt="">
    </swiper-slide>
    <!-- Optional controls -->
    <div class="swiper-pagination"  slot="pagination"></div>
    <!--<div class="swiper-button-prev" slot="button-prev"></div>-->
    <!--<div class="swiper-button-next" slot="button-next"></div>-->
    <!--<div class="swiper-scrollbar"   slot="scrollbar"></div>-->
  </swiper>
</div>
</template>

<script>
    export default{
      name:'HomeSwiper',
      data (){
        return {
          swiperOption:{
            pagination:'.swiper-pagination', //分页
            loop:true                        //支持循环
          },
          swiperList:[
            {
              id:'0001',
              imgUrl:'http://img1.qunarzz.com/piao/fusion/1804/15/9250dbc86a456302.jpg_640x200_4c7220d4.jpg'
            },
            {
              id:'0002',
              imgUrl:'http://img1.qunarzz.com/piao/fusion/1804/7d/8113be89b6c37602.jpg_640x200_878073d9.jpg'
            }
          ]
        }
      }

    }
</script>

<style rel="stylesheet/stylus" lang="stylus" scoped>
  .wrapper >>> .swiper-pagination-bullet-active
    background: #fff !important
  .wrapper
    overflow:hidden
    width: 100%
    height: 0
    padding-bottom:31.25%
    background: #eee;
    .swiper-img
      width: 100%

</style>
