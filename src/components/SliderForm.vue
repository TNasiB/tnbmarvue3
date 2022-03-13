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
        <FrameOne/>
    </swiper-slide>

    <swiper-slide>
        <FrameTwo/>
    </swiper-slide>

    <swiper-slide>
        <FrameThird/>
    </swiper-slide>

    <swiper-slide>
        <FrameFourth/>
    </swiper-slide>

    <swiper-slide>
        <FrameFiveth/>
    </swiper-slide>

    <swiper-slide>
        <FrameSixth/>
    </swiper-slide>

  </swiper>
  <button></button>
</template>

<script>
import { Navigation, Keyboard } from 'swiper'
import { Swiper, SwiperSlide } from 'swiper/vue';
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
  bottom: 200px

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
  height: 100vh
  color: #000
.frame-wrapper 
  height: calc(100vh - 108px)
  background-color: #fff
</style>