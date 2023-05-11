<script>
import SectionIntroduction from "./main_sections/SectionIntroduction.vue"

export default {
  name: "Main",

  components: {
    SectionIntroduction
  }
}
</script>

<template>
  <main>
    <div class="gp-container">
      <SectionIntroduction/>
    </div>
  </main>
</template>

<style lang="scss" scoped>
  main {
    margin-bottom: 500px;
  }
</style>