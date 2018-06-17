<template>
    <div>
      <city-header></city-header>
      <city-search></city-search>
      <city-list :currentCity="currentCity" :cities="cities" :hotCities="hotCities"></city-list>
      <city-alphabet :cityAlphabet="getAlphabet"></city-alphabet>
    </div>
</template>

<script>
import axios from 'axios'
import CityHeader from './components/Header'
import CitySearch from './components/Search'
import CityList from './components/List'
import CityAlphabet from './components/Alphabet'
export default {
  name: 'City',
  components: {CityAlphabet, CityList, CitySearch, CityHeader},
  data () {
    return {
      currentCity: {
        'id': 1,
        'spell': 'beijing',
        'name': '北京'
      },
      cities: {},
      hotCities: []
    }
  },
  mounted () {
    this.getCityInfo()
  },
  methods: {
    getCityInfo () {
      axios.get('/api/city.json')
        .then(this.getCityInfoSucc)
    },
    getCityInfoSucc (res) {
      res = res.data
      if (res.ret && res.data) {
        const data = res.data
        this.cities = data.cities
        this.hotCities = data.hotCities
        this.currentCity = data.currentCity
      }
    }
  },
  computed: {
    getAlphabet () {
      const cityAlphabet = Object.keys(this.cities)
      return cityAlphabet
    }
  }
}
</script>

<style lang="stylus" scoped>

</style>
