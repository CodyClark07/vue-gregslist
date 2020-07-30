<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Home</router-link>|
      <!--Or: <router-link :to="{name: 'About'}">About</router-link> -->
      <router-link to="/about">About</router-link>|
      <router-link to="/cars">Cars</router-link>|
      <router-link to="/jobs">Jobs</router-link>|
      <router-link to="/houses">Houses</router-link>
    </div>
    <router-view />
  </div>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
