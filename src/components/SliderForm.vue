<template>
  <swiper
    :modules="modules"
    navigation
    :allowTouchMove="false"
    :slides-per-view="1"
    :space-between="50"
    @swiper="onSwiper"
    @slideChange="onSlideChange"
  >

    <swiper-slide>
        <FrameOne
        @get-value="getValue"
        />
    </swiper-slide>

    <swiper-slide>
        <FrameTwo
        @get-info="GetData"
        :companies="companies"
        @send-organization="SendOrganization"
        />
    </swiper-slide>

    <swiper-slide>
        <FrameThird
        @set-count="setCount"
        />
    </swiper-slide>

    <swiper-slide>
        <FrameFourth
        :specialists="specialists"
        @add-doctor="addDoctor"
        />
    </swiper-slide>

    <swiper-slide>
        <FrameFiveth
        @set-time="setTime"
        />
    </swiper-slide>

    <swiper-slide>
        <FrameSixth
        :user="user"
        :pacientCount="pacientCount"
        :dateObj="dateObj"
        :organization="organization"
        :activeSpecs="activeSpecs"
        />
    </swiper-slide>

  </swiper>
</template>

<script>
import { Navigation, Keyboard } from 'swiper'
import { Swiper, SwiperSlide } from 'swiper/vue'
import 'swiper/css';

import FrameOne from "./Frame-one.vue"
import FrameTwo from "./Frame-two.vue"
import FrameThird from "./Frame-third.vue"
import FrameFourth from "./Frame-four.vue"
import FrameFiveth from "./Frame-fiveth.vue"
import FrameSixth from "./Frame-sixth.vue"

export default {
  
    name: 'SliderForm',
    components: {
        Swiper,
        SwiperSlide,
        FrameOne,
        FrameTwo,
        FrameThird,
        FrameFourth,
        FrameFiveth,
        FrameSixth,
    },
    props: {
      user: {type: Object},
      pacientCount: {type: Number},
      dateObj: {type: Object},
      companies:{type:Array},
      organization:{type:Object},
      specialists: {type: Array},
      activeSpecs: {type: Array}
    },
    methods:{
      GetData(value){
        this.$emit('get-data',value)
      },
      getValue(user) {
        this.$emit("get-value", user)
      },
      setCount(count) {
        this.$emit("set-count", count)
      },
      setTime(dateObj) {
        this.$emit("set-time", dateObj)
      },
      SendOrganization(organization){
        this.$emit('ship-organization',organization)
      },
      addDoctor(doctor) {
          this.$emit("add-doctor", doctor)
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
        modules: [Navigation, Keyboard], 
      };
    },
};
</script>

<style lang="sass">
.swiper-button-prev, .swiper-button-next
  position: absolute
  z-index: 2
  width: 40px
  height: 40px
  cursor: pointer
  color: #fff
  top: 25px

.swiper-button-prev::after, .swiper-button-next::after
  content: ""
  position: absolute
  width: 40px 
  height: 40px
  background-size: contain
  background-repeat: no-repeat

.swiper-button-prev::after
  background-image: url(../assets/img/arrowleft.svg)

.swiper-button-next::after
  background-image: url(../assets/img/arrowright.svg)

.swiper-button-next
  right: 30px
.swiper-button-prev
  left: 30px
.main
  color: #000
.frame-wrapper
  background-color: #fff
  display: flex
  flex-direction: column
  justify-content: center
  margin-top: 60px
</style>