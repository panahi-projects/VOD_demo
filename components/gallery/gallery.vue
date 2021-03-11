<template>
  <b-container fluid class="gallery-container">
    <b-row v-if="items && items.length">
      <b-col v-for="(i, idx) in items" md="4" :key="idx" class="mb-4">
        <nuxt-link to="/">
          <div class="img-holder">
            <img
              :src="i.ThumbImage ? i.ThumbImage : '/files/images/default.gif'"
              :alt="i.Title"
            />
            <div class="movie-cover"></div>
            <div v-if="i.Categories && i.Categories.length" class="genre-holder">
              <span
                v-for="(catItem, catIdx) in i.Categories"
                :key="catIdx"
                class="genre"
                >{{ catItem.Title }}</span
              >
            </div>
          </div>
          <span class="movie-title">{{ i.Title }}</span>
        </nuxt-link>
      </b-col>
    </b-row>
  </b-container>
</template>
<script>
export default {
  props: ["items"],
};
</script>
<style scoped>
.gallery-container {
  padding: 0;
}
.img-holder {
  width: 100%;
  text-align: center;
  position: relative;
}
.img-holder img {
  width: 100%;
}
.genre-holder {
  position: absolute;
  right: 10px;
  bottom: 10px;
}
.genre {
  padding: 2px 8px;
  margin: 2px;
  display: inline-block;
  color: #ffffff;
  font-size: 10px;
  font-weight: 600;
  background-color: #e41f43;
  border-radius: 4px;
}
.movie-title {
  color: #fff;
  transition: 0.3s;
  width: 100%;
  text-align: center;
  display: block;
  padding: 8px 16px;
}
.movie-title:focus,
.movie-title:hover {
  color: #e41f43;
}
.movie-cover {
  position: absolute;
  background: rgba(0, 0, 0, 0.25);
  background: -moz-linear-gradient(
    top,
    rgb(54, 54, 54, 0.5) 0%,
    rgb(46, 46, 46, 0.2) 50%,
    rgb(38, 38, 38, 0.2) 100%
  );
  background: -webkit-gradient(
    linear,
    left top,
    left bottom,
    color-stop(0%, rgb(54, 54, 54, 0.5)),
    color-stop(50%, rgb(46, 46, 46, 0.2)),
    color-stop(100%, rgb(38, 38, 38, 0.2))
  );
  background: -webkit-linear-gradient(
    top,
    rgb(54, 54, 54, 0.5) 0%,
    rgb(46, 46, 46, 0.2) 50%,
    rgb(38, 38, 38, 0.2) 100%
  );
  background: -o-linear-gradient(
    top,
    rgb(54, 54, 54, 0.5) 0%,
    rgb(46, 46, 46, 0.2) 50%,
    rgb(38, 38, 38, 0.2) 100%
  );

  background: -ms-linear-gradient(
    top,
    rgb(54, 54, 54, 0.5) 0%,
    rgb(46, 46, 46, 0.2) 50%,
    rgb(38, 38, 38, 0.2) 100%
  );
  background: linear-gradient(
    to bottom,
    rgb(54, 54, 54, 0.5) 0%,
    rgb(46, 46, 46, 0.2) 50%,
    rgb(38, 38, 38, 0.2) 100%
  );
  left: 0;
  top: 0;
  right: 0;
  bottom: 0;
  width: 100%;
  height: 100%;
  transition: 1.5s;
  opacity: 0.8;
}
.movie-cover:hover {
  background: -moz-linear-gradient(
    top,
    rgb(46, 46, 46, 0.2) 0%,
    rgb(54, 54, 54, 0.5) 50%,
    #262626 100%
  );
}
</style>
