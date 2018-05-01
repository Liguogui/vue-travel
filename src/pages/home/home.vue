<template>
  <div>
    <home-header></home-header>
    <home-swiper></home-swiper>
    <home-icons></home-icons>
    <home-recomment></home-recomment>
    <home-weekend></home-weekend>
  </div>
</template>

<script>
 import HomeHeader from "./components/Header.vue"
 import HomeSwiper from './components/Swiper.vue'
 import HomeIcons  from './components/Icons.vue'
 import HomeRecomment  from './components/Recommend.vue'
 import HomeWeekend  from './components/Weekend.vue'
export default{
  name:'Home',
  components:{
    HomeHeader,
    HomeSwiper,
    HomeIcons,
    HomeRecomment,
    HomeWeekend
  }
}
</script>

<style scoped>

</style>
