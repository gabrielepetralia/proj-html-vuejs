<script>
import SectionTitle from "../partials/SectionTitle.vue"
import BlogCard from "../partials/cards/BlogCard.vue"

import { blogCards } from "../../data/cardsDB"

export default {
  name: "BlogsSection",

  components: {
    SectionTitle,
    BlogCard
  },

  data() {
    return {
      blogCards
    }
  }
}
</script>

<template>
  <section>
    <div class="gp-container">

      <div class="text-center">
        <SectionTitle
          smallHeader="Enjoi reading on MaxCoach"
          titleBefore="Latest on"
          titleHighlighted="Our Blogs" />
      </div>

      <div class="row row-cols-3 justify-content-between blog-cards-container">
        <BlogCard
          v-for="(blogCard, index) in blogCards"
          :key="index"
          :blogCard="blogCard" />
      </div>

    </div>
  </section>
</template>
  
<style lang="scss" scoped>
@use "../../scss/partials/variables" as *; 

  section {
    padding: 106px 0 100px 0;
    background-color: $my-dark-white;

    .blog-cards-container {
      margin-top: 64px;
    }
  }
</style>