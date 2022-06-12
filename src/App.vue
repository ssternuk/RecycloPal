<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/howitworks">How It Works</router-link> |
      <router-link to="/location">Can I recycle?</router-link> 
      <br />
      <router-link to="/businessinfo">Business Info</router-link> |
      <router-link to="/aboutus">About Us</router-link> |
      <router-link to="/signup">Business sign up</router-link> 
    </div>
    <router-view />
    <Footer />
  </div>
</template>

<script>
  import Footer from "@/components/Footer.vue";
  export default {
    name: "App",
    components: {
      Footer,
    },
  };
</script>

<style>

  #app {
    font-family: "Work Sans", sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #3F7F2B;
    background-color: #F4A79F;
  }

  #nav {
    padding: 30px;
    color: #3F7F2B;
  }

  #nav a {
    font-weight: bold;
    color: #3F7F2B;
  }

  #nav a.router-link-exact-active {
    color: #ffffff;
  }
</style>
