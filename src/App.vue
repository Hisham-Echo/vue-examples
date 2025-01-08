<template>
  <nav>
    <img src="@/assets/logo.png" alt="" />
    <div class="links">
      <router-link to="/">Home</router-link>
      <router-link to="/about">About</router-link>
      <router-link to="/contact">Contact Us</router-link>
      <router-link to="/examples">Examples</router-link>
    </div>
  </nav>
  <router-view />
</template>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

h1 {
  margin-bottom: 20px;
}

* {
  margin: 0;
  padding: 0;
}

nav {
  background-color: #00ff5533;
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 5px 30px;
  // margin-bottom: 20px;

  img {
    max-width: 80px;
  }

  a {
    font-weight: bold;
    color: #2c3e50;
    padding: 15px;
    font-size: 1.25rem;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>

<!-- <script>
export default {
  data: {

  },
};
</script> -->
