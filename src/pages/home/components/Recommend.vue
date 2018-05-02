<template>
  <div>
    <div class="title">热销推荐</div>
    <ul>
      <router-link tag="li" class="item border-bottom"
          :to=" '/detail/' + liItem.id "
          v-for="liItem of recommendList"
          :key="liItem.id">
        <div class="item-img-wrapper">
          <img class="item-img" :src="liItem.imgUrl"
               alt="">
        </div>
        <div class="item-info">
          <p class="item-title">{{liItem.title}}</p>
          <p class="item-desc">{{liItem.desc}}</p>
          <button class="item-btn">查看详情</button>
        </div>
      </router-link>
    </ul>
  </div>
</template>

<script>
    export default{
        name:'HomeRecommend',
        props:{
          recommendList:Array
        },
        data(){
            return{

            }
        }
    }
</script>

<style rel="stylesheet/stylus" lang="stylus" scoped >
  @import "~styles/mixins.styl"
  .title
    height: .8rem
    line-height: .8rem
    background-color: #eee
    text-indent: .2rem
    margin-top:.2rem
  .item
    overflow: hidden
    display: flex
    height: 1.9rem
    .item-img-wrapper
      width: 1.7rem
      height: 1.7rem
      padding: .1rem
      .item-img
        height: 100%
    .item-info
      flex: 1
      padding: .1em
      min-width: 0
      .item-title
        height: .56rem
        line-height: .56rem
        font-size: .32rem
        ellipses()
      .item-desc
        line-height: .6rem
        color: #ccc
        ellipses()
      .item-btn
        line-height:.44rem
        margin-top:.2rem
        background-color: #ff9300
        padding: 0 .2rem
        border-radius: .3rem
        color: #ffffff


</style>
