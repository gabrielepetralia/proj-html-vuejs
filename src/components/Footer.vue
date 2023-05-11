<script>
import { footerMenus } from '../data/menusDB';

export default {
  name: "Footer",

  data() {
    return {
      footerMenus,
    }
  }

}
</script>

<template>
  <footer>
    <div class="gp-container">
      <div class="row">

        <div class="col">
          <h5 class="fw-semibold">Address</h5>

          <ul class="list-unstyled">
            <li>
              <span>382 NE 191st St # 87394 Miami, FL 33179-3899</span>
            </li>
            <li>
              <span>+1 (305) 547-9909 (9am - 5pm EST, Monday - Friday)</span>
            </li>
            <li>
              <a href="#">support@maxcoach.com</a>
            </li>
          </ul>

          <ul class="list-unstyled d-flex social-icons">
            <li v-for="(social, index) in footerMenus.socialMenu" :key="index">
              <a :href="social.href"><i class="social-icon fa-brands" :class="social.icon"></i></a>
            </li>
          </ul>

        </div>

        <div class="col col-menus">
          <div class="row row-cols-3">
            <div v-for="(colMenu, index) in footerMenus.colsMenu" :key="index" class="col">
              <h5 class="fw-semibold">{{ colMenu.label }}</h5>
              <ul class="list-unstyled" :class="{ 'no-label-menu': colMenu.label.length === 0 }">
                <li v-for="(link, index) in colMenu.links" :key="index">
                  <a :href="link.href">{{ link.text }}</a>
                </li>
              </ul>
            </div>
          </div>
        </div>

      </div>

      <div class="credits text-center">
        <span>© 2020 Maxcoach. All Rights Reserved</span>
      </div>

    </div>
  </footer>
</template>

<style lang="scss" scoped>
@use "../scss/partials/variables" as *; 

  footer {
    background-color: $my-dark-white;
    padding: 64px 0 50px 0;

    h5 {
      font-size: 1.1rem;
      color: $my-dark-gray;
      margin-bottom: 12px;
    }

    a,
    span {
      font-size: 0.88rem;
      color: $my-gray;
      line-height: 2.2rem;
    }

    a {

      & .social-icon {
        color: $my-light-gray;
        font-size: 1.5rem;
        margin-right: 31px;
      }
  
      &:hover,
      & .social-icon:hover {
        color: $my-aqua;
      }
    }

    .social-icons {
      margin-top: 20px;
    }
    
    .col-menus {
      padding: 0 160px 0 170px;

      .no-label-menu {
        padding-top: 21px;
      }
    }

    .credits {
      margin-top: 47px;

      & span {
        color: $my-light-gray;
      }
    }
  }

</style>