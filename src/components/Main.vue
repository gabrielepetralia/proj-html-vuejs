<script>
import SectionIntroduction from "./main_sections/SectionIntroduction.vue"
import SectionCourses from "./main_sections/SectionCourses.vue"

export default {
  name: "Main",

  components: {
    SectionIntroduction,
    SectionCourses
  }
}
</script>

<template>
  <main>
    <SectionIntroduction/>
    <SectionCourses/>
  </main>
</template>

<style lang="scss" scoped>
  main {
    margin-bottom: 500px;
  }
</style>