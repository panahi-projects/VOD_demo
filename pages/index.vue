<template>
  <div>
    <p v-if="$fetchState.pending">Fetching Items...</p>
    <p v-else-if="$fetchState.error">An error occurred :(</p>
    <div v-else>
      <b-container fluid>
        <b-row class="mt-5">
          <b-col md="2">
            <asideNavBar />
          </b-col>
          <b-col md="10">
            <carousel />
            <simpleTiles :content="tilesContent" />
            <b-row>
              <b-col md="12">
                <div class="title-bar">
                  <span>FEATURED ARTICLES</span>
                </div>
              </b-col>
            </b-row>
            <gallery :items="featuredItems"></gallery>
          </b-col>
        </b-row>
      </b-container>
    </div>
  </div>
</template>
<script>
import carousel from "~/components/slider/carousel.vue";
import asideNavBar from "~/components/sidenav/asideNavBar.vue";
import simpleTiles from "~/components/tiles/simpleTiles.vue";
import gallery from "~/components/gallery/gallery.vue";
export default {
  components: {
    carousel,
    asideNavBar,
    simpleTiles,
    gallery,
  },
  data() {
    return {
      tilesContent: [
        {
          id: "1",
          title: "Lorem ipsum dolor",
          subtitle: "occaecat cupidatat non proident sunt in culpa",
          imageUrl: "/files/images/banner-img1.jpg",
          link: "/",
        },
        {
          id: "2",
          title: "adipisicing elit sed do eiusmod",
          subtitle: "occaecat cupidatat non proident sunt in culpa",
          imageUrl: "/files/images/banner-img2.jpg",
          link: "/",
        },
        {
          id: "3",
          title: "voluptate velit esse cillum dolore",
          subtitle: "occaecat cupidatat non proident sunt in culpa",
          imageUrl: "/files/images/banner-img3.jpg",
          link: "/",
        },
        {
          id: "4",
          title: "amet conse ctetur",
          subtitle: "occaecat cupidatat non proident sunt in culpa",
          imageUrl: "/files/images/banner-img4.jpg",
          link: "/",
        },
      ],
      featuredItems: [],
    };
  },
  async fetch() {
    try {
      //   if (process.client) {
      var list = await fetch("http://apitest.tek-nic.com/movie/FirstPage").then((res) =>
        res.json()
      );
    //   console.log("list:", list);
      this.featuredItems = list.result[2]?.list; //last movies
      console.log("featuredItems", this.featuredItems);
      //   }
    } catch (ex) {
      console.log(ex);
    }
  },
};
</script>
<style scoped>
.title-bar {
  margin-bottom: 20px;
  padding: 11px 18px 12px;
  background-color: #282828;
  color: #fff;
  font-weight: 600;
}
</style>
