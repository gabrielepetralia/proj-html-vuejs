<script>
import IntroductionSection from "./sections/IntroductionSection.vue"
import CoursesSection from "./sections/CoursesSection.vue"
import TestimonialsSection from "./sections/TestimonialsSection.vue"

export default {
  name: "Main",

  components: {
    IntroductionSection,
    CoursesSection,
    TestimonialsSection
  }
}
</script>

<template>
  <main>
    <IntroductionSection/>
    <CoursesSection/>
    <TestimonialsSection/>
  </main>
</template>

<style lang="scss" scoped>
  
</style>