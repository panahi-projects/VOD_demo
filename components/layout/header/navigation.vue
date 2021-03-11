<template>
  <div class="main-navbar" :class="toggleMenu ? 'main-navbar-toggle' : '' ">
    <div @click="toggleMenu = !toggleMenu" class="mobile-hamburger">
      <font-awesome-icon icon="bars"/>
    </div>
    <ul>
      <li v-for="(navItem, navIdx) in menuItems" :key="navIdx">
        <span :id="'menuItem_' + navItem.id">
          <nuxt-link :to="navItem.link">{{ navItem.title }}</nuxt-link>
        </span>
      </li>
    </ul>
  </div>
</template>
<script>
export default {
  data() {
    return {
      toggleMenu:false,
      menuItems: [
        {
          id: "1",
          title: "Home",
          link: "/",
        },
        {
          id: "2",
          title: "Celebrities",
          link: "/",
        },
        {
          id: "3",
          title: "Gallery",
          link: "/",
        },
        {
          id: "4",
          title: "News",
          link: "/",
        },
        {
          id: "5",
          title: "Contacts",
          link: "/",
        },
      ],
    };
  },
};
</script>
<style scoped>
.main-navbar {
  position: relative;
  text-align: right;
}
.main-navbar ul {
  margin: 0;
  padding: 0;
}
.main-navbar ul li {
  list-style-type: none;
  display: inline-block;
}
.main-navbar ul li:first-child {
  border-left: 1px solid #000;
}
.main-navbar ul li a {
  font-family: "Righteous", sans-serif, monospace, tahoma;
  font-size: 24px;
  text-align: center;
  display: inline-block;
  padding: 24px 22px;
  border-right: 1px solid #000;
}
.main-navbar ul li a:hover,
.main-navbar ul li a:focus,
.main-navbar ul li a:active {
  background: #2e2e2e;
  background: -moz-linear-gradient(bottom, #363636 0%, #2e2e2e 50%, #262626 100%);
  background: -webkit-gradient(
    linear,
    left bottom,
    left top,
    color-stop(0%, #363636),
    color-stop(50%, #2e2e2e),
    color-stop(100%, #262626)
  );
  background: -webkit-linear-gradient(bottom, #363636 0%, #2e2e2e 50%, #262626 100%);
  background: -o-linear-gradient(bottom, #363636 0%, #2e2e2e 50%, #262626 100%);
  background: -ms-linear-gradient(bottom, #363636 0%, #2e2e2e 50%, #262626 100%);
  background: linear-gradient(to top, #363636 0%, #2e2e2e 50%, #262626 100%);
  filter: progid:DXImageTransform.Microsoft.gradient(startColorstr='#262626',endColorstr='#363636',GradientType=0);
}
.mobile-hamburger{
  display:none;
}
@media only screen and (max-width:968px){
  .main-navbar ul li a {
    font-size: 18px;
    padding: 18px 14px;
  }
}
@media only screen and (max-width:798px){
  .mobile-hamburger{
    display:inline-block;
    /* position:absolute; */
    transform:translateY(-25px);
    cursor:pointer;
  }
  .mobile-hamburger *{
    width:25px;
  }
  .main-navbar ul{
    position: absolute;
    z-index: 999;
    right: -25px;
    top: 25px;
    background-color:#202020;
    width: 75%;
    box-shadow: 1px 1px 8px rgba(0,0,0,0.5);
    transition:0.5s;
    transform-origin: top right;
    transform: scale(0);
  }
  .main-navbar-toggle ul{
    transform: scale(1);
  }
  .main-navbar ul li a,
  .main-navbar ul li:first-child,
  .main-navbar ul li{
    display: block;
    border:none;
  }
  .main-navbar ul li a{
    border-bottom: 1px solid #242424;
  }
}
</style>
