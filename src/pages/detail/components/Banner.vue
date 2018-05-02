<template>
  <div>
      <div class="banner" @click="handleBannerClick">
        <img  class="banner-img"
              src="//img1.qunarzz.com/sight/p0/201308/08/41150dacc0e3a0c8c8d65eac.jpg_600x330_37602849.jpg"
              alt="">
        <div class="banner-info">
          <div class="banner-title">北京动物园(AAAA景区)</div>
          <div class="banner-number">
            <span class="iconfont banner-icon">&#xe6dd;</span>
            9
          </div>
        </div>
      </div>
    <common-gallary :imgs="imgs" v-show="showGallary" @close="handGallayClose"></common-gallary>
  </div>
</template>

<script>
  import CommonGallary from 'common/gallary/Gallary'
    export default{
        name:'DetailBanner',
        data(){
            return{
              imgs:['http://img1.qunarzz.com/sight/p0/201308/08/41150dacc0e3a0c8c8d65eac.jpg_r_800x800_16d497dc.jpg',
                'http://img1.qunarzz.com/sight/p0/1412/ef/f05ecd25f3ab3b395580cf7a0c249490.water.jpg_r_800x800_15974661.jpg',
                'http://img1.qunarzz.com/sight/p0/1412/8e/8775702489e6dba06d775233c574216b.water.jpg_r_800x800_3e543d32.jpg'],
              showGallary:false
            }
        },
        components: {
          CommonGallary
        },
        methods:{
          handleBannerClick(){
            this.showGallary = true
          },
          handGallayClose(){
            this.showGallary = false
          }
        }
    }
</script>

<style rel="stylesheet/stylus" lang="stylus" scoped>
  .banner
    position:relative
    overflow: hidden
    height: 0
    padding-bottom:55%
    .banner-img
      width: 100%
    .banner-info
      display: flex
      position: absolute
      left: 0
      right: 0
      bottom: 0
      line-height: .6rem
      color:#fff
      background-image: linear-gradient(to bottom,rgba(0,0,0,0),rgba(0,0,0,.8))

      .banner-title
        flex: 1
        font-size: .32rem
        padding:0 .2rem
      .banner-number
        height: .32rem
        line-height: .32rem
        margin-top: .14rem
        padding:0 .4rem
        border-radius: .2rem
        background-color: rgba(0,0,0,.8)
        font-size: .24rem
        .banner-icon
          font-size: .24rem
</style>
