<template>
  <div id="app">
    <div>
      <SiteHeader/>
    </div>
    <div>
      <SiteMain/>
    </div>
  </div>
</template>

<script>


import SiteHeader from './components/SiteHeader.vue';
import SiteMain from './components/SiteMain.vue';


export default {
  name: 'App',
  components: {
    SiteHeader,
    SiteMain
  }
}
</script>

<style lang="scss">

@import './assets/variables.scss';
@import "../node_modules/bootstrap/scss/bootstrap.scss";

body { 
  font-family: "Lato"; 
  }
// #app {
//   font-family: Avenir, Helvetica, Arial, sans-serif;
//   -webkit-font-smoothing: antialiased;
//   -moz-osx-font-smoothing: grayscale;
//   text-align: center;
//   color: #2c3e50;
//   margin-top: 60px;
// }
</style>
