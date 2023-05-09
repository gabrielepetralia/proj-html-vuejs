<script>
import "@fortawesome/fontawesome-free/css/all.css"
import "@fortawesome/fontawesome-free/js/all.js"

import Header from "./components/Header.vue"
import Jumbotron from "./components/Jumbotron.vue"
import Main from "./components/Main.vue"
import Footer from "./components/Footer.vue"

export default {
  name : "App",

  components : {
    Header,
    Jumbotron,
    Main,
    Footer
  }
}
</script>

<template>
  <div class="container">
    <Header/>
    <Jumbotron/>
    <Main/>
    <Footer/>
  </div>
</template>

<style lang="scss">
  @use "bootstrap/scss/bootstrap.scss";
  @use "./scss/main.scss";
</style>