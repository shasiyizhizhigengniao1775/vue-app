<template>
  <div id="app">
    <Header></Header>
    <router-view class="main" />
    <Footer></Footer>
  </div>
</template>

<script>
import Header from "./components/Header";
import Footer from "./components/Footer";
export default {
  components: {
    Header,
    Footer,
  },
};
</script>
<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  .main {
    margin: 1rem 0;
  }
}

a {
  font-weight: bold;
  color: #000000;

  &.router-link-exact-active {
    color: #ffffff;
  }
}
</style>
