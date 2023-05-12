<script>
export default {
  name: "GoUpBtn",

  data() {
    return {
      btnVisible: false,
      lastScrollY: null
    }
  },

  methods: {
    addVisible() {
      window.addEventListener("scroll", () => {
        // window.scrollY >= 300 ? this.btnVisible = true : this.btnVisible = false;
        if (window.scrollY > this.lastScrollY ) {
          this.btnVisible = false
        } else if( window.scrollY >= 100) {
          this.btnVisible = true
        } else {
          this.btnVisible = false
        }

        this.lastScrollY = window.scrollY;
      })
    },

    removeVisible() {
      window.addEventListener("scroll", () => {
        window.scrollY >= 300 ? this.btnVisible = true : this.btnVisible = false;
      })
    },

    // goUp() {
    //   window.addEventListener("scroll", () => {
    //     const btn = document.querySelector(".go-up-btn")
    //     console.log(btn)
    //     if(btn.classList.includes("btn-visible")) {
    //       btn.addEventListener("click", () => {
    //         document.documentElement.scrollTop = 0;
    //       })
    //     }
    //   })
    // }

    goUp() {
      document.documentElement.scrollTop = 0;
    }
  },

  mounted() {
    this.addVisible();
  }
}
</script>

<template>
  <div @click="goUp" class="go-up-btn text-center" :class="{'btn-visible' : btnVisible}">
    <i class="fa-solid fa-arrow-up"></i>
  </div>
</template>

<style lang="scss" scoped>
  @use "../../scss/partials/variables" as *;

  .go-up-btn {
    opacity: 0;
    position: fixed;
    bottom: 88px;
    right: 24px;
    height: 61px;
    width: 61px;
    line-height: 61px;
    color: white;
    border-radius: 50%;
    background-color: $my-aqua;
    box-shadow: 0 0 20px 4px rgba(0,0,0,0.06);
    transition: all 0.3s;

    &.btn-visible {
      opacity: 1;

      &:hover {
        cursor: pointer;
      }
    }
  }
</style>