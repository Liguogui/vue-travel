<template>
  <div class="icons">
    <swiper>

      <swiper-slide v-for="(page,index) of pages" :key="index">
        <div class="icon" v-for="item of page" :key="item.id">
          <div class="icon-img">
            <img class="icon-img-content" :src="item.imgUrl"
                  alt="">
          </div>
          <p class="icon-desc">{{item.desc}}</p>
        </div>
      </swiper-slide>

    </swiper>
  </div>
</template>

<script>
    export default{
        name:'HomeIcons',
        data(){
            return{
              iconList:[
                {
                  id:'001',
                  imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
                  desc:'景点门票'
                },
                {
                  id:'002',
                  imgUrl:'http://img1.qunarzz.com/piao/fusion/1804/ed/cf572be30fc32f02.png',
                  desc:'Q+精选'
                },
                {
                  id:'003',
                  imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/b1/528a9e80403b8c02.png',
                  desc:'杭州乐园'
                },
                {
                  id:'004',
                  imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/75/eca3ce656c886502.png',
                  desc:'千岛湖'
                },
                {
                  id:'005',
                  imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
                  desc:'景点门票'
                },
                {
                  id:'006',
                  imgUrl:'http://img1.qunarzz.com/piao/fusion/1804/ed/cf572be30fc32f02.png',
                  desc:'Q+精选'
                },
                {
                  id:'007',
                  imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/b1/528a9e80403b8c02.png',
                  desc:'杭州乐园'
                },
                {
                  id:'008',
                  imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/75/eca3ce656c886502.png',
                  desc:'千岛湖'
                },
                {
                  id:'009',
                  imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/b8/c5dcdb58deec2402.png',
                  desc:'西溪湿地'
                }
              ]
            }
        },
        computed:{
          pages (){
            const pages = [];
            this.iconList.forEach(function (item,index) {
              const page = Math.floor(index/8);
              if(!pages[page]){
                pages[page] = []
              }
              pages[page].push(item)
            });
            return pages
          }
        }

    }
</script>

<style rel="stylesheet/stylus" lang="stylus" scoped>
    @import "~styles/varibles.styl"
    @import "~styles/mixins.styl"
    .icons >>> .swiper-container
      height: 0
      padding-bottom:50%
    /*margin-top: .1rem*/
    /*overflow:hidden*/
    /*width: 100%*/
    /*height: 0*/
    /*padding-bottom: 50%*/
    /*background-color: green*/
    .icon
      position:relative
      overflow:hidden
      float: left;
      width: 25%
      height: 0
      padding-bottom 25%
      /*background-color: red*/
      .icon-img
        position:absolute
        top:0
        left:0
        right:0
        bottom:.44rem
        /*background-color: blue*/
        box-sizing:border-box
        padding:.06rem
        .icon-img-content
          display:block
          margin: 0 auto
          height: 100%
      .icon-desc
        position:absolute
        left:0
        right:0
        bottom:0
        height: .44rem
        line-height: .44rem
        color:$darkTextColor
        text-align:center
        ellipses()

</style>
