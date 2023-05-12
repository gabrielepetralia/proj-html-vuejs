<script>
import IntroductionSection from "./sections/IntroductionSection.vue"
import CoursesSection from "./sections/CoursesSection.vue"
import TestimonialsSection from "./sections/TestimonialsSection.vue"
import BlogsSection from "./sections/BlogsSection.vue"
import CtaSection from "./sections/CtaSection.vue"

export default {
  name: "Main",

  components: {
    IntroductionSection,
    CoursesSection,
    TestimonialsSection,
    BlogsSection,
    CtaSection
  }
}
</script>

<template>
  <main>
    <IntroductionSection/>
    <CoursesSection/>
    <TestimonialsSection/>
    <BlogsSection/>
    <CtaSection/>
  </main>
</template>

<style lang="scss" scoped>
  
</style>