<template>
  <div>
    <city-header></city-header>
    <city-search :cities="cities"></city-search>
    <city-list :cities="cities"
               :hotCities="hotCities"
               :letter="letter"
    >

    </city-list>
    <city-alphabet :cities="cities"
                   @change="handLetterChange"
    ></city-alphabet>
  </div>
</template>

<script>
    import axios from 'axios'
    import CityHeader from './components/Header.vue'
    import CitySearch from './components/Search.vue'
    import CityList from './components/List.vue'
    import CityAlphabet from './components/Alphabet.vue'
    export default{
        name:'City',
        data(){
            return{
              hotCities:[],
              cities:{},
              letter:''
            }
        },
        components:{
          CityHeader,
          CitySearch,
          CityList,
          CityAlphabet
        },
        methods:{
          handLetterChange(letter){
              this.letter = letter
          },
          getCityInfo(){
            axios.get('/api/city.json')
                 .then(this.getCityInfoSucc)
          },
          getCityInfoSucc(res){
            res = res.data;
            if(res.ret && res.data){
              const data = res.data;
              this.hotCities = data.hotCities;
              this.cities = data.cities;
            }
          }
        },
        mounted(){
          this.getCityInfo()
        }
    }
</script>

<style rel="stylesheet/stylus" lang="stylus" scoped>

</style>
