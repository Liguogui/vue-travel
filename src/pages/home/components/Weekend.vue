<template>
  <div>
    <div class="title">周末去哪儿</div>
    <ul>
      <li class="item border-bottom"
          v-for="liItem of recommendList"
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
    data(){
      return{
        recommendList:[
          {
            id:'001',
            imgUrl:'http://img1.qunarzz.com/sight/source/1505/4e/3e87ee62e59cdb.jpg_r_640x214_fe6cc902.jpg',
            title:'“最忆是杭州”- G20峰会特别版《印象西湖》',
            desc:'灯光效果绝佳，唯美与震撼并存，如果说是看灯光秀，那她是完美的。'
          },
          {
            id:'002',
            imgUrl:'http://img1.qunarzz.com/sight/source/1505/4e/3e87ee62e59cdb.jpg_r_640x214_fe6cc902.jpg',
            title:'“最忆是杭州”- G20峰会特别版《印象西湖》',
            desc:'灯光效果绝佳，唯美与震撼并存，如果说是看灯光秀，那她是完美的。'
          },
          {
            id:'003',
            imgUrl:'http://img1.qunarzz.com/sight/source/1505/4e/3e87ee62e59cdb.jpg_r_640x214_fe6cc902.jpg',
            title:'“最忆是杭州”- G20峰会特别版《印象西湖》',
            desc:'灯光效果绝佳，唯美与震撼并存，如果说是看灯光秀，那她是完美的。'
          }
        ]
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
    .item-img-wrapper
      overflow: hidden
      width: 100%
      height: 0
      padding-bottom:33.9%
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

