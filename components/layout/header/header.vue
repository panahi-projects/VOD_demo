<template>
  <div class="main-header">
    <b-container fluid>
      <b-row>
        <b-col cols="12">
          <b-row class="p-4">
            <b-col lg="8" md="7" sm="12" class="pb-2">
              <div class="profile-login">
                <ul>
                  <li>
                    <nuxt-link to="/">
                      <span>Login</span>
                    </nuxt-link>
                  </li>
                  <li>
                    <nuxt-link to="/">
                      <span>Entries</span>
                    </nuxt-link>
                  </li>
                </ul>
              </div>
            </b-col>
            <b-col lg="4" md="5" sm="12">
              <searchbar></searchbar>
            </b-col>
          </b-row>
        </b-col>
      </b-row>
      <b-row>
        <b-container fluid class="navbar">
          <b-col lg="4" md="4">
            <logo></logo>
          </b-col>
          <b-col lg="8" md="8">
            <navigation></navigation>
          </b-col>
        </b-container>
      </b-row>
    </b-container>
  </div>
</template>
<script>
import logo from "~/components/layout/header/logo.vue";
import navigation from "~/components/layout/header/navigation.vue";
import searchbar from "~/components/layout/header/searchbar.vue";
export default {
  components: {
    logo,
    navigation,
    searchbar,
  },
};
</script>
<style scoped>
.main-header {
  background-color: transparent;
  color: #f1f1f1;
}
.profile-login ul {
  margin: 0;
  padding: 0;
}
.profile-login ul li {
  list-style-type: none;
  display: inline-block;
  padding: 0 8px;
}
.navbar {
  background: #363636;
  background: -moz-linear-gradient(top, #363636 0%, #2e2e2e 50%, #262626 100%);
  background: -webkit-gradient(
    linear,
    left top,
    left bottom,
    color-stop(0%, #363636),
    color-stop(50%, #2e2e2e),
    color-stop(100%, #262626)
  );
  background: -webkit-linear-gradient(top, #363636 0%, #2e2e2e 50%, #262626 100%);
  background: -o-linear-gradient(top, #363636 0%, #2e2e2e 50%, #262626 100%);
  background: -ms-linear-gradient(top, #363636 0%, #2e2e2e 50%, #262626 100%);
  background: linear-gradient(to bottom, #363636 0%, #2e2e2e 50%, #262626 100%);
  filter: progid:DXImageTransform.Microsoft.gradient(startColorstr='#363636',endColorstr='#262626',GradientType=0);
  padding-top: 0;
  padding-bottom: 0;
}
</style>
