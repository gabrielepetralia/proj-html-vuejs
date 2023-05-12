<script>
import { headerMenu } from "../data/menusDB"
import MenuItem from "./partials/MenuItem.vue"

export default {
  name: "Header",

  components: {
    MenuItem
  },

  data() {
    return {
      lightLogo : "light-logo.png",
      darkLogo: "dark-logo.png",
      headerMenu,
      headerFixed: false
    }
  },

  methods: {
    getImage(img) {
      return new URL(`../assets/img/${img}`, import.meta.url).href
    },

    addFixed() {
      window.addEventListener( "scroll", () => {
        window.scrollY>=200 ? this.headerFixed = true : this.headerFixed  = false;
      })
    }
  },

  mounted() {
    this.addFixed();
  }
  
}
</script>

<template>
  <header :class="{'header-fixed' : headerFixed}">
    <div class="gp-container">

      <div class="row align-items-center justify-content-between">
        
        <div class="col-auto logo">
          <img v-if="!headerFixed" class="img-fluid" :src="getImage(lightLogo)" alt="MaxCoach Logo">
          <img v-else class="img-fluid" :src="getImage(darkLogo)" alt="MaxCoach Logo">
        </div>
  
        <nav class="col-auto d-flex align-items-center h-100">
          <ul class="list-unstyled d-flex align-items-center mb-0 h-100">
            <MenuItem
              v-for="(menuItem, index) in headerMenu"
              :key="index"
              :menuItem="menuItem"
              :headerFixedItem="headerFixed" />
          </ul>
  
          <div class="icons-menu d-flex align-items-center">
            <i class="icon fa-solid fa-cart-shopping"></i>
            <div class="cart-counter">0</div>
            <i class="icon fa-regular fa-circle-user"></i>
          </div>

          <div class="col-auto d-flex align-items-center ms-2">
            <div class="searchbar input-group rounded overflow-hidden mb-0">
              <input type="text" class="form-control border-0 rounded-0" placeholder="Search...">
              <button class="btn btn-outline-secondary border-0 rounded-0 px-3" type="button">
                <i class="lens fa-solid fa-magnifying-glass"></i>
              </button>
            </div>
          </div>

        </nav>
  
      </div>

    </div>
  </header>
</template>

<style lang="scss" scoped>
@use "../scss/partials/variables" as *; 

  header {
    position: absolute;
    width: 100%;
    top: 0;
    left: 0;
    z-index: 900;
    background-color: $my-blue;
    transition: position 0.5s ease-in-out;

    .row {
      height: 80px;
    }

    .logo {
      &:hover {
        cursor: pointer;
      }

      img {
        width: 160px;
      }
    }

    .icons-menu {
      position: relative;
      
      .icon {
        font-size: 18px;
        padding: 0 11px;
        color: white;

        &:first-child {
          padding-right: 16px;
        }

        &:hover {
          cursor: pointer;
        }
      }
      .cart-counter {
        position: absolute;
        top: -10px;
        left: 24px;
        color: $my-dark-gray;
        background-color: white;
        border-radius: 50%;
        width: 15px;
        height: 15px;
        text-align: center;
        line-height: 15px;
        font-size: 0.7rem;
        padding-right : 1.3px;
        border: 1px solid $my-blue;
      }
    }


    .searchbar {
      height: 48px;
      width: 196px;

      &:focus-within {
        border : 1px solid $my-aqua;
      }

      .form-control {
        font-size: 0.9rem;
        padding-left: 22px;
        background-color: white;

        &:focus {
          box-shadow: none;
        }
      }

      button {
        background-color: white;
        transition: all 0.3s;

        &:hover {
          background-color: $my-aqua;
        }
        .lens {
          color: $my-aqua;
          transition: all 0.2s;
        }
        &:hover .lens {
          color: white
        }
      }

    }

    &.header-fixed {
      position: fixed;
      top: 0;
      left: 0;
      background-color: white;
      box-shadow: 0 0 20px 12px rgba(0,0,0,0.08);

      .icons-menu {
        .icon {
          color: $my-blue;
        }

        .cart-counter {
          color: white;
          background-color: $my-blue;
          border: 1px solid white;
        }
      }

      .searchbar {
        .form-control {
          background-color: $my-dark-white;
        }
      }

      button {
        background-color: $my-dark-white;
      }

    }
  }
</style>