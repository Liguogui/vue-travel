<template>
  <div>
    <home-header></home-header>
    <home-swiper :swiperList="swiperList"></home-swiper>
    <home-icons :iconList="iconList"></home-icons>
    <home-recomment :recommendList="recommendList"></home-recomment>
    <home-weekend :weekendList="weekendList"></home-weekend>
  </div>
</template>

<script>
 import HomeHeader from "./components/Header.vue"
 import HomeSwiper from './components/Swiper.vue'
 import HomeIcons  from './components/Icons.vue'
 import HomeRecomment  from './components/Recommend.vue'
 import HomeWeekend  from './components/Weekend.vue'
 import axios from 'axios'
 import { mapState } from 'vuex'

export default{
  name:'Home',
  components:{
    HomeHeader,
    HomeSwiper,
    HomeIcons,
    HomeRecomment,
    HomeWeekend
  },
  data() {
    return {
      lastCity:'',
      swiperList:[],
      iconList:[],
      recommendList:[],
      weekendList:[]
    }
  },
  methods:{
    getHomeInfo(){
      axios.get('/api/index.json?city='+this.city)
           .then(this.getHomeInfoSucc)
    },
    getHomeInfoSucc(res){
      res = res.data;
      if(res.ret && res.data){
        const data = res.data;
        this.swiperList = data.swiperList;
        this.iconList = data.iconList;
        this.recommendList = data.recommendList;
        this.weekendList = data.weekendList;
      }
    }
  },
  mounted(){
    console.log('mounted');
    this.lastCity = this.city;
    this.getHomeInfo()
  },
  activated(){ //页面重新被显示的时候
    console.log('activated');
    if(this.lastCity !== this.city){
      this.lastCity = this.city;
      this.getHomeInfo();
    }
  },
  computed:{
    ...mapState(['city'])
  }
}
</script>

<style scoped>

</style>
