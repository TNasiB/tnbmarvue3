<template>
  <div id="app">
    <HeaderNav/>
    <SliderForm
    @get-data="GetData"
    @get-value="getValue"
    @set-count="setCount"
    :user="user"
    :pacientCount="pacientCount"
    />
  </div>
</template>

<script>
import HeaderNav from "./components/HeaderNav"
import SliderForm from "./components/SliderForm"

export default {
  name: 'App',
  components: {
    SliderForm,
    HeaderNav,
  },
  data(){
    return{
      companies:{},
      user: {},
      pacientCount: 300,
    }
  },
  methods:{
    GetData(value){
      let query = value;

      fetch(`https://search-maps.yandex.ru/v1/?text=${query}&type=biz&lang=ru_RU&apikey=d81da452-d93b-4e52-afd1-27aa7282013f`)
      .then(response=>response.json())
      .then(data=>(this.companies=data))
      console.log(this.companies.features[1].properties.name)
      console.log(this.companies.features[1].properties.description) // запрос
    },
    getValue(user) {
      this.user = user
    },
    setCount(count) {
      this.pacientCount = count
    }
  },
  setup() {
      const onSwiper = (swiper) => {
        console.log(swiper);
      };
      const onSlideChange = () => {
        console.log('slide change');
      };
      return {
        onSwiper,
        onSlideChange,
      };
  },
}
</script>

<style lang="sass">
*
  margin: 0
  padding: 0
  font-family: 'Roboto'
  box-sizing: border-box
a
  color: inherit
  text-decoration: none
  font-size: inherit
li
  font-size: inherit
  color: inherit
  list-style-type: none
button
  cursor: pointer
input
  border: none
body
  overflow-y: hidden
button.radio
  border-radius: 50%
  width: 35px
  height: 35px
  border: 5px solid #fff
  background-color: #fff
  box-shadow: 0px 0px 3px #000
  cursor: pointer
button.radio.active
  background-color: #75D7CD
.flex 
  display: flex
.flex-column 
  display: flex
  flex-direction: column
.container
  max-width: 1368px
  margin: 0 auto
  padding: 0 15px
.shadow 
  webkit-box-shadow: 0px 14px 14px 0px rgba(34, 60, 80, 0.2)
  -moz-box-shadow: 0px 14px 14px 0px rgba(34, 60, 80, 0.2)
  box-shadow: 0px 14px 14px 0px rgba(34, 60, 80, 0.2)
.title 
  font-size: 40px
  color: #004D45
  padding-left: 20px
  text-align: center
  text-transform: uppercase
  margin: 20px 60px 0
</style>

