<template>
  <div id="app">
    <router-view />
  </div>
</template>

<style lang="scss">
@import "../node_modules/reset-css/reset.css";

@font-face {
  font-family: "Rotonda C";
  src: url("./assets/fonts/RotondaC.woff");
}

html {
  overflow-x: hidden;
}
body {
  position: relative;
  overflow-x: hidden;
}

#app {
  font-family: "Rotonda C", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
}
</style>
