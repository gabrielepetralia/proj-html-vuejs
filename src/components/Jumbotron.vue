<script>
export default {
  name: "Jumbotron",

  methods : {
    getImage(img) {
      return new URL(`../assets/img/${img}`, import.meta.url).href
    },
  }
}
</script>

<template>
  <div class="jumbotron">
    <div class="gp-container">
    </div>
  </div>
</template>

<style lang="scss" scoped>
@use "../scss/partials/variables" as *;  

  .jumbotron {
    height: 800px;
    background-color: $my-blue;
  }

</style>