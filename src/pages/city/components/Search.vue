<template>
  <div>
    <div class="search">
      <input v-model="keyword" class="search-input" type="text" placeholder="输入城市名或拼音"
      >
    </div>
    <div class="search-content" ref="search" v-show="keyword">
      <ul>
        <li
          class="search-item border-bottom"
          v-for="item of list"
          :key="item.id"
          @click="handCityClick(item.name)"
        >{{item.name}}</li>
        <li class="search-item border-bottom" v-show="hasNoData">没有找到匹配数据</li>
      </ul>
    </div>
  </div>
</template>

<script>
  import { mapState,mapMutations } from 'vuex'
    import BScroll from 'better-scroll'
    export default{
        name:'CitySearch',
        props:{
          cities:Object
        },
        data(){
            return{
              keyword:'',
              list:[],
              timer:null
            }
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
        },
        computed:{
          hasNoData(){
            return !this.list.length
          }
        },
        watch:{
          keyword(){
            if(this.timer){
              clearTimeout(this.timer)
            }
            if(!this.keyword){
                this.list = [];
                return;
            }
            let me = this;
            this.timer = setTimeout(function () {
              const result = [];
              for (let i in me.cities){
                  me.cities[i].forEach(function (value) {
                    if(value.spell.indexOf(me.keyword) >-1 ||
                        value.name.indexOf(me.keyword) >-1
                    ){
                      result.push(value);
                    }
                  });
              }
              me.list = result;
            },100);
          }
        },
        mounted(){
          this.scroll = new BScroll(this.$refs.search);
        }
    }
</script>

<style rel="stylesheet/stylus" lang="stylus" scoped>
  @import "~styles/varibles.styl"
  .search
    height: .72rem
    padding: 0 .1rem
    background-color: $bgColor
    .search-input
      box-sizing: border-box
      width: 100%
      height: .62rem
      line-height: .62rem
      padding:0 .1rem
      text-align: center
      border-radius: .06rem
      color: #666
  .search-content
    z-index:1
    overflow: hidden
    position: absolute
    top: 1.58rem
    left: 0
    right: 0
    bottom: 0
    background-color: #eee
    .search-item
      line-height: .62rem
      padding-left: .2rem
      background-color: #fff
      color: #666
</style>
