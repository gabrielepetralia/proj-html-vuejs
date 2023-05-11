<script>
import SectionTitle from "../partials/SectionTitle.vue"
import CourseCard from "../partials/cards/CourseCard.vue"

import { courseCards } from "../../data/cardsDB"

export default {
  name: "SectionCourses",

  components: {
    SectionTitle,
    CourseCard
  },

  data() {
    return {
      courseCards
    }
  }
}
</script>

<template>
  <section>
    <div class="gp-container">
      <div class="row">
        <div class="col text-center">
          <SectionTitle
            smallHeader="Choose a course to get started"
            titleBefore="Latest Featured"
            titleHighlighted="Courses" />
        </div>

        <div class="row row-cols-2 course-cards-container">
          <CourseCard
          v-for="(courseCard, index) in courseCards"
          :key="index"
          :courseCard="courseCard" />
        </div>

        <div class="view-courses-btn d-flex justify-content-center">
          <button class="gp-btn rounded fw-bold">
            View all courses
            <i class="arrow fa-solid fa-arrow-right"></i>
          </button>
        </div>
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
@use "../../scss/partials/variables" as *; 

  section {
    background-color: $my-dark-white;
    padding: 98px 0 94px 0;

    .course-cards-container {
      margin-top: 6px;
    }

    .view-courses-btn {
      margin-top: 18px;

      button {
        padding: 16px 70px;

        .arrow {
          padding-top: 3px;
          margin-left: 3px;
        }
      }
    }
  }
</style>