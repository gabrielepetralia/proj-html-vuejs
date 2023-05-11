<script>
import SectionTitle from "../partials/SectionTitle.vue"
import SwiperTestimonials from "../partials/SwiperTestimonials.vue"

import { sponsorsList } from "../../data/listsDB"

export default {
  name: "TestimonialsSection",

  components: {
    SectionTitle,
    SwiperTestimonials
  },

  data() {
    return {
      sponsorsList
    }
  },

  methods : {
    getImage(img) {
      return new URL(`../../assets/img/${img}`, import.meta.url).href
    }
  }
}
</script>

<template>
  <section>
    <div class="gp-container">
      <div class="row flex-column">

        <div class="col text-center">
          <SectionTitle
            titleBefore="Why People Talk About"
            titleHighlighted="MaxCoach"
            titleAfter="?" />
        </div>

        <SwiperTestimonials/>

        <div class="row sponsors align-items-center">
          <div v-for="(sponsor, index) in sponsorsList" :key="index" class="col text-center">
            <img :src="getImage(sponsor)">
          </div>
        </div>

      </div>
    </div>
  </section>
</template>

<style lang="scss" sccoped>

  section {
    padding: 70px 0 90px 0;
    background-color: white;

    .swiper {
      margin-top: 46px;
    }

    .sponsors {
      margin-top: 102px;

      & img {
        transition: all 0.3s;
      }

      & img:hover {
        filter: saturate(0);
      }
    }
  }
</style>