<script>
export default {
  name: "MenuItem",

  props : {
    menuItem : Object
  }
}
</script>

<template>
  <li class="header-menu-item h-100 d-flex align-items-center">
    <a class="text-white header-menu-link" :href="menuItem.href">{{ menuItem.text }}
      <i class="chevron text-white fa-solid fa-chevron-down"></i>
    </a>
    <ul class="gp-dropmenu gp-dropdown list-unstyled">
      <li
        class="gp-dropmenu-item gp-dropdown-item d-flex justify-content-between align-items-center"
        v-for="(dropdownItem, index) in menuItem.dropdown"
        :key="index"
        :class="{ 'has-dropend': dropdownItem.dropend.length > 0 }">
        <a :href="dropdownItem.href">{{ dropdownItem.text }}</a>
        <i v-if="dropdownItem.dropend.length > 0" class="chevron chevron-r fa-solid fa-chevron-right"></i>
        <ul v-if="dropdownItem.dropend.length > 0" class="gp-dropmenu gp-dropend list-unstyled">
          <li
            v-for="(dropendItem, index) in dropdownItem.dropend"
            :key="index"
            class="gp-dropmenu-item gp-dropend-item d-flex justify-content-between align-items-center">
            <a :href="dropendItem.href">{{ dropendItem.text }}</a>
          </li>
        </ul>
      </li>
    </ul>
  </li>
</template>


<style lang="scss" scoped>
@use "../../scss/partials/variables" as *; 

  .header-menu-item {
    position: relative;
    margin-left: 36px;
    overflow: hidden;

    .chevron {
      font-size: 0.6rem;
      padding-bottom: 2px;
      margin-left: 2px;
    }

    & .header-menu-link::after {
      content: '';
      position: absolute;
      width: 100%;
      transform: scaleX(0);
      height: 1px;
      bottom: 0;
      left: 0;
      background-color: white;
      transform-origin: bottom right;
      transition: transform 0.25s ease-out;
    }

    &:hover .header-menu-link::after {
      transform: scaleX(1);
      transform-origin: bottom left;
    }

    & a {
      position: relative;
      font-size: 0.99rem;
      font-weight: 500;
    }

    &:hover {
      cursor: pointer;
      overflow: visible;
    }

    .gp-dropmenu {
      position: absolute;
      z-index: 999;
      width: 250px;
      padding: 16px 0;
      border-bottom: 4px solid $my-aqua;
      opacity: 0;
      transition: top 0.3s, opacity 0.4s ;

      &.gp-dropdown {
        background-color: $my-dark-white;
        top: 100px;
        left: -20px;
      }

      &.gp-dropend {
        background-color: white;
        top: 4px;
        left: 250px;
      }

      .gp-dropmenu-item {
        position: relative;
        padding: 7px 30px;

        a,
        .chevron-r {
          color: $my-gray;
        }

        &.gp-dropdown-item:hover>a,
        &.gp-dropend-item:hover>a,
        &:hover .chevron-r {
          color: black;
        }

        &.has-dropend:hover .gp-dropend {
          top: -16px;
          opacity: 1;
        }
      }
    }

    &:hover .gp-dropdown {
      opacity: 1;
      top: 80px;
    }
  }
</style>