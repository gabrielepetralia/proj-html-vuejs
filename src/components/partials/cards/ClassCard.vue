<script>
export default {
  name: "ClassCard",

  props: {
    classCard: Object
  }
}
</script>

<template>
  <div class="col px-0">
    <div class="class-card">
      <a href="">

        <i class="class-card-icon fa-solid" :class="classCard.icon"></i>
  
        <div class="class-card-text">
          <h5 class="fw-semibold">{{ classCard.title }}</h5>
          <p>{{ classCard.text }}</p>
        </div>

      </a>
    </div>
  </div>
</template>

<style lang="scss" scoped>
  @use "../../../scss/partials/variables" as *; 

  .class-card {
    
    .class-card-icon {
      font-size: 3.8rem;
      color: $my-dark-gray;
      margin-bottom: 25px
    }

    .class-card-text {
      padding-right: 42px;

      h5 {
        font-size: 1.2rem;
        color: $my-dark-gray;
        margin-bottom: 10px;
      }

      p {
        font-size: 0.95rem;
        line-height: 1.6rem;
        color: $my-gray;
      }
    }
  }
</style>