<script>

export default {
  name: "TestimonialCard",

  props: {
    testimonialCard: Object
  },

  methods: {
    getImage(img) {
      return new URL(`../../../assets/img/${img}`, import.meta.url).href
    }
  }
}
</script>

<template>
  <div class="col d-flex justify-content-center">
    <div class="testimonial-card d-flex align-items-center rounded">

      <div class="col-auto img-col">
        <a class="testimonial-card-img d-flex align-items-center justify-content-center">
          <img :src="getImage(testimonialCard.img)">
        </a>
        <img class="dots" :src="getImage('dots.png')">
      </div>

      <div class="col">
        <div class="testimonial-card-text">
          <p>{{ testimonialCard.text }}</p>
          <span class="fw-bold name">{{ testimonialCard.name }}</span>
          <span class="profession">/ {{ testimonialCard.profession }}</span>
        </div>
      </div>

      </div>
  </div>
</template>

<style lang="scss" scoped>
@use "../../../scss/partials/variables" as *; 

  .testimonial-card {
    max-width: 1000px;
    background-color: white;

    .img-col {
      position: relative;
      
      .testimonial-card-img {
        height: 202px;
        width: 202px;
        border-radius: 50%;
        overflow: hidden;
        margin-right: 100px;

        img {
          height: 100%;
          z-index: 99;
        }
      }
      
      .dots {
        width: 130px;
        position: absolute;
        top: 100px;
        left: 120px;
      }
    }

    .testimonial-card-text {
      p {
        font-size: 2.1rem;
        margin-bottom: 32px;
      }

      .name {
        display: block;
        font-size: 0.95rem;
        color: $my-dark-gray;
        letter-spacing: 0.15px;
        margin-bottom: 12px;
        text-transform: uppercase;
      }
  
      .profession {
        font-size: 0.9rem;
        color: $my-light-gray;
      }
    }
  }
</style>