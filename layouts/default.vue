<template>
  <div>
    <div class="main-wrapper">
      <header>
        <main-header />
      </header>
      <b-container fluid class="main-content">
        <nuxt />
      </b-container>
    </div>
    <footer>
      <main-footer />
    </footer>
  </div>
</template>
<script>
import header from "~/components/layout/header/header.vue";
import footer from "~/components/layout/footer/footer.vue";
export default {
  components: {
    "main-header": header,
    "main-footer": footer,
  },
};
</script>
<style>
@import url('https://fonts.googleapis.com/css2?family=Lato&family=Righteous&display=swap');
html {
  font-family: "Source Sans Pro", -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto,
    "Helvetica Neue", Arial, sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}

*,
*:before,
*:after {
  box-sizing: border-box;
  margin: 0;
}
a {
  color: #fff;
  -webkit-transition: color 0.3s;
  -moz-transition: color 0.3s;
  -o-transition: color 0.3s;
  transition: color 0.3s;
  text-decoration: none !important;
  outline: none;
  font-size: 14px;
  font-weight: 500;
}
a:hover,
a:focus {
  color: #e41f43;
}
body {
  background-color: #171717;
  padding: 18px 0 0 0;
  position: relative;
  color: #8c8c8c;
}
.main-wrapper {
  background: #333333;
  margin: 0 auto;
  width: auto;
  position: relative;
  z-index: 1;
}
.main-content {
  padding: 8px 16px;
}
footer {
  margin: 0 auto;
  width: auto;
}
@media (min-width: 1200px) {
  footer,
  .main-wrapper {
    max-width: 1230px;
  }
}
</style>
