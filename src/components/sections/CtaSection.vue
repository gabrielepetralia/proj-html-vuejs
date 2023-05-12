<script>
import SectionTitle from "../partials/SectionTitle.vue"

export default {
  name: "CtaSection",

  components: {
    SectionTitle
  }
}
</script>

<template>
  <section>
    <div class="gp-container text-center">

      <SectionTitle
        titleBefore="Start today for getting"
        titleHighlighted="Online Certification" 
        class="ctaTitle"/>

      <h1 class="fw-semibold">You can be your own guiding star with our help!</h1>

      <button class="gp-btn rounded fw-bold">Get started now</button>

    </div>
  </section>
</template>

<style lang="scss" scoped>
  section {
    padding: 90px 0 100px 0;
    background-color: white;

    .ctaTitle {
      transform: scale(0.48)
    }

    h1 {
      font-size: 1.9rem;
      margin: -48px 0 25px 0;
    }
  }
</style>