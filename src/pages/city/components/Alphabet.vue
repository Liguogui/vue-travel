<template>
    <ul class="list">
      <li class="item"
          v-for="item of letters"
          :key="item"
          :ref= 'item'
          @click="handLetterClick"
          @touchstart="handleTouchStart"
          @touchmove="handleTouchMove"
          @touchend="handleTouchEnd"
      >
        {{item}}
      </li>
    </ul>
</template>

<script>
    export default{
        name:'CityAlphabet',
        props:{
          cities:Object
        },
        computed:{
          letters(){
            const letters = [];
            for(let i in this.cities){
              letters.push(i)
            }
            return letters; //['A','B'...'Z']
          }
        },
        data(){
            return{
              touchStatus:false  //标识位
            }
        },
        methods:{
          handLetterClick(e){
            this.$emit('change',e.target.innerText);
          },
          handleTouchStart(){
            this.touchStatus = true;
          },
          handleTouchMove(e){
            if(this.touchStatus){
//              e.touches[0]表示手指的一些信息
              const startY = this.$refs['A'][0].offsetTop;
              const touchY = e.touches[0].clientY;
              const distandtouchY = touchY - 79;
              const index = Math.floor((distandtouchY - startY)/20);
//              console.log(index);
//              console.log(this.letters[index]);
              if(index >= 0 && index < this.letters.length){
                this.$emit('change',this.letters[index]);
              }
//              console.log(e.touches[0]);
//              console.log(e.touches);
            }
          },
          handleTouchEnd(){
            this.touchStatus = false;
          }
        }
    }
</script>

<style rel="stylesheet/stylus" lang="stylus" scoped>
  @import "~styles/varibles.styl"
  .list
    display: flex
    flex-direction: column
    justify-content: center
    position: absolute
    top: 1.58rem
    right: 0
    bottom: 0
    width: .4rem
    .item
      line-height: .4rem
      text-align: center
      color: $bgColor

</style>
