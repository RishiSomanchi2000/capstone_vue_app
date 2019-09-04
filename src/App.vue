<template>
  <div id="app">
    <body id="body" class="body-wrapper boxed-menu" >
      <div id="preloader" class="smooth-loader-wrapper">
      <div class="smooth-loader">
          <div class="loader1">
              <div class="loader-target">
                  <div class="loader-target-main"></div>
                  <div class="loader-target-inner"></div>
              </div>
          </div>
      </div>
  </div>
      <router-view/>
    </body>
  </div>


</template>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
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
