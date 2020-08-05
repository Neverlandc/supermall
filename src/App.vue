<template>
  <div id="app">
    <router-view/>
    <main-tab-bar/>
  </div>
</template>

<script>
import MainTabBar from 'components/content/MainTabBar/MainTabBar'
import router from './router/index'

export default {
  name: 'App',
  router,
  components: {
    MainTabBar
  }
}
</script>

<style scoped>
  @import "assets/css/base.css";
</style>
