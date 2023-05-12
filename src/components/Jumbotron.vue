<script>
export default {
  name: "Jumbotron",

  data() {
    return {
      ytVideo: {
        img: "yt-video.jpg",
        href: "https://www.youtube.com/watch?v=ElFJ1qcl74U&ab_channel=ThemeMove"
      }
    }
  },

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
      <div class="row justify-content-center">
        <div class="col text-center">
          <h1 class="fw-bold text-white">Learn At Your Own Pace!</h1>
          <p class="fw-semibold">Get teamed up with people of the same will.</p>

          <button class="gp-btn rounded fw-bold">Get started for free</button>

          <div class="yt-video-container d-flex justify-content-center align-items-center">
            <div class="yt-video overflow-hidden">
              <a :href="ytVideo.href">
                <img class="yt-logo" :src="getImage('yt-logo.png')" alt="YT Logo">
                <img class="img-fluid" :src="getImage(ytVideo.img)">
              </a>
            </div>
          </div>

        </div>
      </div>
    </div>

    <div class="jumbo-images d-flex justify-content-between align-items-baseline">
      <img class="jumbo-left-img" :src="getImage('jumbo-left.png')">
      <img class="jumbo-right-img" :src="getImage('jumbo-right.png')">
    </div>

  </div>
</template>

<style lang="scss" scoped>
@use "../scss/partials/variables" as *;  

  .jumbotron {
    position: relative;
    height: 800px;
    background-color: $my-blue;
    padding-top: 176px;

    h1 {
      font-size: 2.83rem;
    }

    p {
      font-size: 1.14rem;
      color: rgb(177, 177, 177);
    }

    button:hover {
      color: $my-aqua;
      background-color: white;
    }

    .yt-video-container {
      position: absolute;
      left: 50%;
      transform: translate(-50%);
      bottom: -91px;
      aspect-ratio: 1.66;
      width: 85%;
      max-width: 770px;
      margin: 0 auto;
      box-shadow: 0 0 20px 12px rgba(0,0,0,0.08);
      border-radius: 20px;
      background-color: white;
      padding: 20px;
      overflow: hidden;

      &:hover img:not(.yt-logo) {
        transform: scale(1.1);
      }
      
      img:not(.yt-logo) {
        width: 100%;
        height: 100%;
        object-fit: cover;
        transition: all 1s;
      }

      .yt-logo {
        position: absolute;
        left: 50%;
        transform: translate(-50%, 286%);
        width: 90px;
        z-index: 900;
      }
    }

    .jumbo-images {
      width: 77.5%;
      margin: 52px auto 0;

      .jumbo-right-img {
        margin-right: 116px;
        height: 355px;
      }

      .jumbo-left-img {
        padding-bottom: 52px;
      }
    }
  }
</style>