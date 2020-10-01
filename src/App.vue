<template>
  <div id="app">
    <NavBar />
    <MainContent />
    <Footer />
  </div>
</template>

<script>
import NavBar from './components/NavBar.vue'
import MainContent from './components/MainContent.vue'
import Footer from './components/Footer.vue'

export default {
  name: 'App',
  components: {
    NavBar,
    MainContent,
    Footer
  }
}
</script>