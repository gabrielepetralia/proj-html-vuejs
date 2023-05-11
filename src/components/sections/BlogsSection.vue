<script>
import SectionTitle from "../partials/SectionTitle.vue"

export default {
  name: "BlogsSection",

  components: {
    SectionTitle
  },
}
</script>

<template>
  <section>
    <!-- <div class="gp-container">

      <div class="text-center">
        <SectionTitle
          smallHeader="Enjoi reading on MaxCoach"
          titleBefore="Latest on"
          titleHighlighted="Our Blogs" />
      </div>

      <div class="row">
        
      </div>

    </div> -->
  </section>
</template>
  
<style lang="scss" scoped>
@use "../../scss/partials/variables" as *; 

  section {
    padding: 106px 0 90px 0;
    background-color: $my-dark-white;

  }
</style>