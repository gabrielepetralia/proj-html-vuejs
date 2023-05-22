<script>
import SectionTitle from "../partials/SectionTitle.vue"
import ClassCard from "../partials/cards/ClassCard.vue"

import { classCards } from "../../data/cardsDB"

export default {
  name : "ClassesSection",

  components: {
    SectionTitle,
    ClassCard
  },

  data() {
    return {
      classCards
    }
  },

  methods: {
    getImage(img) {
      return new URL(`../../assets/img/${img}`, import.meta.url).href
    }
  }

}
</script>

<template>
  <section>
    <div class="gp-container">

      <div class="text-center">
        <SectionTitle
          smallHeader="Wanna transform your life?"
          titleBefore="Glad to"
          titleHighlighted="Help you"
          titleAfter="Learn" />
      </div>

      <div class="row row-cols-4 justify-content-between class-cards-container">
        <ClassCard
          v-for="(classCard, index) in classCards"
          :key="index"
          :classCard="classCard" />
      </div>

      <img :src="getImage('services-background.png')">
      
    </div>
  </section>
</template>

<style lang="scss" scoped>
@use "../../scss/partials/variables" as *; 

  section {
    position: relative;
    padding: 94px 0 570px 0;
    background: linear-gradient(white, $my-dark-white);

    .class-cards-container {
      margin-top: 87px;
    }

    img {
      width: 90%;
      max-width: 1110px;
      position: absolute;
      left: 50%;
      transform: translate(-50%);
      bottom: -30px;
    }
  }
</style>