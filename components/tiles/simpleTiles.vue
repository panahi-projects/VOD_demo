<template>
  <b-container fluid="lg" class="simple-tiles">
    <b-row v-if="content">
      <b-col
        v-for="(contentItem, contentIdx) in content"
        lg="6"
        md="6"
        sm="12"
        class="tile-holder"
        :key="contentIdx"
      >
        <div class="tile-container">
          <img :src="contentItem.imageUrl" :alt="contentItem.title" />
          <div class="image-hover-cover"></div>
          <div class="tile-title">
            <h6>
              {{ contentItem.title }}
            </h6>
            <span class="subtitle">
              {{ contentItem.subtitle }}
            </span>
          </div>
        </div>
      </b-col>
    </b-row>
  </b-container>
</template>
<script>
export default {
  props: ["content"],
  data() {
    return {};
  },
};
</script>
<style scoped>
.tile-holder {
  margin-bottom: 32px;
}
.simple-tiles {
  margin-top: 22px;
  padding: 0;
  text-align: center;
}
.tile-container {
  position: relative;
  cursor: pointer;
  width: 100%;
}
.image-hover-cover {
  position: absolute;
  background: rgba(0, 0, 0, 0.25);
  left: 0;
  top: 0;
  right: 0;
  bottom: 0;
  width: 100%;
  height: 100%;
  transition: 0.5s;
  opacity: 0.8;
  transform: scale(1);
}
.tile-container:hover .image-hover-cover {
  transform: scale(0.85);
  position: absolute;
}
.tile-title {
  color: #fff;
  text-transform: uppercase;
  font-family: "Lato", "Arial", sans-serif;
  position: absolute;
  bottom: 10%;
  width: 100%;
}
.tile-title .subtitle,
.tile-title h6 {
  width: 85%;
  text-align: center;
  margin: auto;
}
.tile-title h6 {
  font-size: 26px;
  font-weight: 600;
}
.tile-title .subtitle {
  font-size: 12px;
  color: #e41f43;
}
@media only screen and (max-width:968px){
    .tile-holder,
    .simple-tiles{
        overflow: hidden;
    }
    
}
</style>
