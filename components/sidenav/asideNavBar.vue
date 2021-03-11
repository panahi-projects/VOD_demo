<template>
  <div class="aside-nav">
    <ul>
      <li v-for="(sideItem, sideIdx) in sideItems" :key="sideIdx">
        <nuxt-link :to="sideItem.link" :id="sideItem.id">
          <span>{{ sideItem.title }}</span>
        </nuxt-link>
      </li>
    </ul>
  </div>
</template>
<script>
export default {
  data() {
    return {
      sideItems: [
        {
          id: "1",
          title: "Actors",
          link: "/",
        },
        {
          id: "2",
          title: "Actresses",
          link: "/",
        },
        {
          id: "3",
          title: "Authors",
          link: "/",
        },
        {
          id: "4",
          title: "Directors",
          link: "/",
        },
        {
          id: "5",
          title: "Haiti",
          link: "/",
        },
        {
          id: "6",
          title: "MLB Teams",
          link: "/",
        },
        {
          id: "7",
          title: "Models",
          link: "/",
        },
        {
          id: "8",
          title: "Music Groups",
          link: "/",
        },
        {
          id: "9",
          title: "NBA Teams",
          link: "/",
        },
        {
          id: "10",
          title: "NFL Teams",
          link: "/",
        },
        {
          id: "11",
          title: "NHL Teams",
          link: "/",
        },
        {
          id: "12",
          title: "Singers",
          link: "/",
        },
        {
          id: "13",
          title: "Tennis Players",
          link: "/",
        },
        {
          id: "14",
          title: "TV Presenters",
          link: "/",
        },
        {
          id: "15",
          title: "TV Shows",
          link: "/",
        },
        {
          id: "16",
          title: "Wrestlers",
          link: "/",
        },
      ],
    };
  },
};
</script>
<style scoped>
.aside-nav ul {
  padding: 0;
  margin: 0;
}
.aside-nav ul li {
  display: block;
  list-style-type: none;
}
.aside-nav ul li a {
  font-family: "Lato", "Arial", sans-serif;
  font-size: 19px;
  font-weight: 500;
  background-color:#232323;
  color: #fff;
  display: inline-block;
  width:100%;
  padding:6px 12px;
  border-bottom: 1px solid #2f2f2f;
  transition:0.4s;
}
.aside-nav ul li a:focus,
.aside-nav ul li a:hover{
    background-color: #e41f43;
}

@media only screen and (max-width:968px){
  .aside-nav ul li a {
    font-size: 14px;
  }
}
</style>
