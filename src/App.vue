<script>
import "@fortawesome/fontawesome-free/css/all.css"
import "@fortawesome/fontawesome-free/js/all.js"

import Header from "./components/Header.vue"
import Jumbotron from "./components/Jumbotron.vue"
import Main from "./components/Main.vue"
import Footer from "./components/Footer.vue"
import GoUpBtn from "./components/partials/GoUpBtn.vue"

export default {
  name: "App",

  components: {
    Header,
    Jumbotron,
    Main,
    Footer,
    GoUpBtn
  }
}
</script>

<template>
  <Header/>
  <Jumbotron/>
  <Main/>
  <Footer/>
  <GoUpBtn/>
</template>

<style lang="scss">
  @use "./scss/main.scss";
</style>