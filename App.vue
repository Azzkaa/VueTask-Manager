<template>
  <div id="app">
    <MainNavbar />
    <router-view />
  </div>
</template>

<script>
import MainNavbar from './components/MainNavbar.vue'

export default {
  name: 'App',
  components: {
    MainNavbar
  }
}
</script>

<style>
/* Global styles, including your main background */
* {
  margin: 0;
  padding: 0;
}

#app {
  width: 100%;
  background: url('https://images.pexels.com/photos/376533/pexels-photo-376533.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1');
  background-position: center;
  background-size: cover;
  height: 100vh;
}
</style>
