<template>
    <div>
      <detail-banner></detail-banner>
      <detail-header></detail-header>
      <div class="content"></div>
    </div>
</template>

<script>
    import DetailBanner from './components/Banner.vue'
    import DetailHeader from './components/Header.vue'
    export default{
        name:'Detail',
        data(){
            return{

            }
        },
        components:{
          DetailBanner,
          DetailHeader
        }
    }
</script>

<style rel="stylesheet/stylus" lang="stylus" scoped>
  .content
    height: 50rem
</style>
