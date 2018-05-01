<template>
  <div>
    <div class="title">周末去哪儿</div>
    <ul>
      <li class="item border-bottom"
          v-for="liItem of weekendList"
          :key="liItem.id">
        <div class="item-img-wrapper">
          <img class="item-img" :src="liItem.imgUrl"
               alt="">
        </div>
        <div class="item-info">
          <p class="item-title">{{liItem.title}}</p>
          <p class="item-desc">{{liItem.desc}}</p>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
  export default{
    name:'HomeWeekend',
    props:{
      weekendList:Array
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
  .item
    .item-img-wrapper
      overflow: hidden
      width: 100%
      height: 0
      padding-bottom:37.09%
      .item-img
        width:100%
    .item-info
      padding:.1rem
      .item-title
        height: .56rem
        line-height: .56rem
        font-size: .32rem
        ellipses()
      .item-desc
        line-height: .6rem
        color: #ccc
        ellipses()


</style>

