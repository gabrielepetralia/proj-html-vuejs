<script>
export default {
  name: "SectionTitle",

  props: {
    smallHeader: String,
    titleBefore: String,
    titleHighlighted: String,
    titleAfter: String
  }
}
</script>

<template>
  <div class="section-title">
    <p class="fw-semibold">{{ smallHeader }}</p>
    <h1 class="fw-bold">{{ titleBefore }} <span class="fw-light">{{ titleHighlighted }}</span> {{ titleAfter }}</h1>
  </div>
</template>

<style lang="scss" scoped>
@use "../../scss/partials/variables" as *; 

  p {
      text-transform: uppercase;
      color: $my-light-gray;
      letter-spacing: 1.2px;
    }

    h1 {
      font-size: 3rem;
      text-transform: capitalize;
      color: $my-dark-gray;
      margin-bottom: 40px;

      span {
        color: $my-aqua;
      }
    }
</style>