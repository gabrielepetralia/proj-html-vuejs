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
      headerMenu
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
  <header>
    <div class="gp-container">

      <div class="row align-items-center justify-content-between">
        
        <div class="col-auto logo">
          <img class="img-fluid" :src="getImage(lightLogo)" alt="">
        </div>
  
        <nav class="col-auto d-flex align-items-center h-100">
          <ul class="list-unstyled d-flex align-items-center mb-0 h-100">
            <MenuItem v-for="(menuItem, index) in headerMenu" :key="index" :menuItem="menuItem"/>
          </ul>
  
          <div class="icons-menu d-flex align-items-center">
            <i class="icon text-white fa-solid fa-cart-shopping"></i>
            <div class="cart-counter">0</div>
            <i class="icon text-white fa-regular fa-circle-user"></i>
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
    background-color: $my-blue;

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
        background-color: white;
        border-radius: 50%;
        width: 15px;
        height: 15px;
        text-align: center;
        line-height: 15px;
        font-size: 0.7rem;
        border: 1px solid black;
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
  }
</style>