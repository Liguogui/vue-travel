<template>
    <div class="list" ref="wrapper">
      <div class="area-wrap">

        <div class="area">
          <div class="title border-topbottom">当前城市</div>
          <div class="button-list">
            <div class="button-wrap"
                 @click="handCityClick(currentCity)"
            >
              <div class="button">{{this.currentCity}}</div>
            </div>
          </div>
        </div>

        <div class="area">
          <div class="title border-topbottom">热门城市</div>
          <div class="button-list">
            <div class="button-wrap"
                 v-for="item of hotCities"
                 :key="item.id"
                 @click="handCityClick(item.name)"
            >
              <div class="button">{{item.name}}</div>
            </div>
          </div>
        </div>

        <div class="area"
             v-for="(item,key,index) of cities"
             :key="key"
             :ref="key"
        >
          <div class="title border-topbottom">{{key}}</div>
          <ul class="item-list">
            <li class="item border-bottom"
                v-for="city of item"
                :key="city.id"
                @click="handCityClick(city.name)"
            >
              {{city.name}}
            </li>
          </ul>
        </div>

      </div>
    </div>
</template>

<script>
  import { mapState,mapMutations } from 'vuex'
  import BScroll from 'better-scroll'
//  const wrapper = document.querySelector('.wrapper')
//  const scroll = new BScroll(wrapper)
  export default{
    name:'CityList',
    props:{
      hotCities: Array,
      cities: Object,
      letter:String
    },
    data(){
        return{

        }
    },
    mounted(){
      this.scroll = new BScroll(this.$refs.wrapper);
    },
    watch:{
      letter (){
        if(this.letter){
          let element = this.$refs[this.letter];  //v-for中的ref是个数组
//          console.log(element);
          this.scroll.scrollToElement(element[0])
        }
      }
    },
    computed:{
      ...mapState({
        currentCity:'city'
      })
    },
    methods:{
      handCityClick(city){
  //        this.$store.commit('changeCity',city);
        this.changeCity(city);
        this.$router.push('/');
      },
      ...mapMutations({
        changeCity:'changeCity'
      })
    }
  }
</script>

<style rel="stylesheet/stylus" lang="stylus" scoped>
  @import "~styles/varibles.styl"
  .list
    position:absolute
    top: 1.58rem
    left: 0
    right: 0
    bottom: 0
    overflow: hidden
    .border-topbottom
      &:before
        border-color: #ccc
      &:after
        border-color: #ccc
    .title
      line-height: .54rem
      background-color: #eee
      padding-left: .2rem
      color: #666
      font-size: .26rem
    .button-list
      padding: .1rem .6rem .1rem .1rem
      overflow: hidden
      .button-wrap
        float:left
        width: 33.33%
        .button
          margin: .1rem
          padding: .1rem 0
          text-align: center
          border: .02rem solid #ccc
          border-radius: .06rem
    .item-list
      .item
        line-height: .76rem
        color: #666
        padding-left: .2rem
      .border-bottom
        &:before
          border-color: #ccc

</style>
