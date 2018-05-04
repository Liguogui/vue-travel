<template>
<div class="wrapper">
  <swiper :options="swiperOption" v-if="showSwiper">
    <!-- slides -->
    <swiper-slide v-for="item of swiperList"
                  :key="item.id"
    >
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

<script type='text/ecmascript-6'>
    export default{
      name:'HomeSwiper',
      props:{
        swiperList:Array
      },
      data (){
        return {
          swiperOption:{
            pagination:'.swiper-pagination', //分页
            loop:true                        //支持循环
          }
        }
      },
      computed:{
        showSwiper(){
          return this.swiperList.length
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
