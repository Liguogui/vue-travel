<template>
  <div>
    <div class="title">热销推荐</div>
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
          <button class="item-btn">查看详情</button>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
    export default{
        name:'HomeRecommend',
        data(){
            return{
              recommendList:[
                {
                  id:'001',
                  imgUrl:'http://img1.qunarzz.com/sight/p0/1709/28/288fbeccc335f774a3.img.jpg_200x200_4a81bde9.jpg',
                  title:'“最忆是杭州”- G20峰会特别版《印象西湖》',
                  desc:'灯光效果绝佳，唯美与震撼并存，如果说是看灯光秀，那她是完美的。'
                },
                {
                  id:'002',
                  imgUrl:'http://img1.qunarzz.com/sight/p0/1709/28/288fbeccc335f774a3.img.jpg_200x200_4a81bde9.jpg',
                  title:'“最忆是杭州”- G20峰会特别版《印象西湖》',
                  desc:'灯光效果绝佳，唯美与震撼并存，如果说是看灯光秀，那她是完美的。'
                },
                {
                  id:'003',
                  imgUrl:'http://img1.qunarzz.com/sight/p0/1709/28/288fbeccc335f774a3.img.jpg_200x200_4a81bde9.jpg',
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
