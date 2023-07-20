<template>
  <div id="app">
    <navigation> </navigation>
    <Banner/>
    <router-view/>
  </div>
</template>
<script> 
import Nav from '@/components/Nav.vue'
import Banner from '@/components/Banner.vue'
export default {
    name: 'nav-name',
    // props: {},
    data: function(){
        return {}
    },
    // computed: {},
    //methods: {}
    // watch: {},
    components: {
      "navigation": Nav,
      Banner,
    },
    // mixins: [],
    // filters: {},
    // -- Lifecycle Methods
    // -- End Lifecycle Methods 
}
 </script>
<style>
body {
  background: black;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
}
</style>
