<template>
  <div id="app">
    <AppToolbar />
      <router-view />
    <AppFooter />
  </div>
</template>

<script>
import AppToolbar from './components/AppToolbar'
import AppFooter from './components/AppFooter'

export default {
  name: 'App',
  components: {
    AppToolbar,
    AppFooter
  }
}
</script>

<style>
  html, body {
    height: 100%;
  }
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
}
</style>
