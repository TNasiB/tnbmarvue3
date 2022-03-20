<template>
  <div id="app">
    <HeaderNav
    />

    <SliderForm
    @get-data="GetData"
    @get-value="getValue"
    @set-count="setCount"
    @set-time="setTime"
    @add-doctor="addDoctor"
    @ship-organization="ShipOrganization"
    :user="user"
    :cost="cost"
    :pacientCount="pacientCount"
    :dateObj="dateObj"
    :specialists="specialists"
    :activeSpecs="activeSpecs"
    :companies="companies"
    :organization="organization"
    />
  </div>
</template>

<script>
import HeaderNav from "./components/HeaderNav"
import SliderForm from "./components/SliderForm"
import specialists from "./assets/specialists.json";

export default {
  name: 'App',
  components: {
    SliderForm,
    HeaderNav,
  },
  data(){
    return{
      companies:[],
      user: {},
      pacientCount: 300,
      dateObj: {},
      organization: {}, 
      specialists: specialists,
      activeSpecs: [],
      costArray: [],
      cost: 0,
    }
  },
  methods: {
    GetData(value){
      let query = value;

      fetch(`https://search-maps.yandex.ru/v1/?text=${query}&type=biz&lang=ru_RU&apikey=d81da452-d93b-4e52-afd1-27aa7282013f`)
      .then(response=>response.json())
      .then(data=>(this.companies=data.features))
      console.log(this.companies)
    },
    getValue(user) {
      this.user = user
    },
    setCount(count) {
      this.pacientCount = +count
      this.computeCost()
    },
    setTime(dateObj) {
      this.dateObj = dateObj
      this.dateObj.date = String(this.dateObj.date.split("-").reverse()).replaceAll(",", ".")
    },
    ShipOrganization(organization) {
      this.organization = organization
    },
    addDoctor(doctor) {
      let isContain = this.activeSpecs.some(spec => spec.title == doctor.title)
      if (!isContain) {
        this.activeSpecs.push(doctor)
      } else {
        let findResult = this.activeSpecs.find(item => item.title == doctor.title)
        let index = this.activeSpecs.indexOf(findResult)
        this.activeSpecs[index] = doctor
      }
      this.computeCost()
    },
    computeCost() {
      this.cost = 0
      for (let i = 0; i < this.activeSpecs.length; i++) {
        this.costArray[i] = this.activeSpecs[i].cost * this.pacientCount
      }
      this.costArray.forEach(item => this.cost += item)
    }
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
  // overflow-y: hidden
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
@media (max-width:900px)
  .title
    font-size: 30px
@media (max-width:640px)
  .title
    font-size: 20px
</style>

