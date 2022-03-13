<template>
  <div id="app">
    <HeaderNav/>
    <SliderForm/>
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
  margin: 40px 0
  padding-left: 20px
</style>

