<script>
export default {
  name: "ServiceCard",

  props: {
    serviceCard: Object
  },

  methods: {
    getImage(img) {
      return new URL(`../../../assets/img/${img}`, import.meta.url).href
    }
  }
}
</script>

<template>
  <div class="col">
    <div class="service-card d-flex flex-column rounded" :class="{'service-card-reverse' : serviceCard.reverse}">
      <div class="service-card-text">
        <h5 class="fw-semibold">{{ serviceCard.title }}</h5>
        <p>{{ serviceCard.text }}</p>
      </div>
      <div class="service-card-img">
        <img :src="getImage(serviceCard.img)">
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@use "../../../scss/partials/variables" as *; 

  .service-card {
    background-color: white;
    width: 272px;
    padding: 36px 18px 0 4px;
    margin-bottom: 30px;
    box-shadow: 0 0 20px 4px rgba(0,0,0,0.06);
    
    h5 {
      font-size: 1.2rem;
      color: $my-blue;
    }

    p {
      font-size: 0.95rem;
      line-height: 1.6rem;
      color: $my-gray;
    }

    .service-card-text {
      padding-left: 19px;
    }
  }

  .service-card-reverse {
    padding: 25px 20px 0 0;
    flex-direction: column-reverse !important;

    .service-card-img {
      margin-bottom: 16px
    }

    .service-card-text {
      padding-left: 23px;
    }
  }
</style>