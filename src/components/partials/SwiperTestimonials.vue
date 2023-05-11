<script>
import TestimonialCard from "../partials/cards/TestimonialCard.vue"
import { testimonialCards } from "../../data/cardsDB"

import { Swiper, SwiperSlide } from "swiper/vue";
import { EffectFade } from "swiper";

import "swiper/css";
import "swiper/css/effect-fade";

export default {
  name: "SwiperTestimonials",

  components: {
    Swiper,
    SwiperSlide,
    TestimonialCard
  },

  setup() {
    return {
      modules: [ EffectFade ],
    }
  },

  data() {
    return {
      testimonialCards
    }
  }
}
</script>

<template>
  <swiper
    :spaceBetween="30"
    :effect="'fade'"
    :loop="true"
    :modules="modules"
    class="mySwiper"
  >
    <swiper-slide v-for="(testimonialCard, index) in testimonialCards" :key="index">
      <TestimonialCard :testimonialCard="testimonialCard"/>
    </swiper-slide>
  </swiper>
</template>

<style lang="scss">

</style>