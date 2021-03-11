<template>
  <div>
    <slider animation="fade" class="slider-container" style="height:380px">
      <slider-item
        v-for="(item, index) in list"
        :key="index"
        :style="item"
        @click="hello"
      >
        <div class="image-container">
          <img :src="`/files/images/${item.imagename}`" alt="" />
          <div class="slider-title">
            <span class="main-title" v-html="item.mainTitle"></span>
            <span class="sub-title" v-html="item.subtitle"> </span>
          </div>
        </div>
      </slider-item>
    </slider>
  </div>
</template>
<script>
// import { Slider, SliderItem } from "vue-easy-slider";
export default {
  // components: {
  //   Slider,
  //   SliderItem,
  // },
  data() {
    return {
      list: [
        {
          backgroundColor: "#333333",
          width: "100%",
          height: "414px",
          imagename: "slides1-970x414.jpg",
          mainTitle: "Lorem ipsum dolor sit amet conse",
          subtitle:
            "Aliquam dapibus tincidunt metus. Praesent justo dolor, lobortis quis, lobortis...",
        },
        {
          backgroundColor: "#333333",
          width: "100%",
          height: "414px",
          imagename: "slides2-970x414.jpg",
          mainTitle: "consectetur adipiscing elit, sed do",
          subtitle:
            "Aliquam dapibus tincidunt metus. Praesent justo dolor, lobortis quis, lobortis...",
        },
        {
          backgroundColor: "#333333",
          width: "100%",
          height: "414px",
          imagename: "slides3-970x414.jpg",
          mainTitle: "eiusmod tempor incididunt ut labore",
          subtitle:
            "Aliquam dapibus tincidunt metus. Praesent justo dolor, lobortis quis, lobortis...",
        },
      ],
    };
  },
  methods: {
    hello($event) {
      console.log(`hello index: ${$event}`);
    },
  },
};
</script>
<style scoped>
.slider-container {
  height: 380px;
}
.image-container {
  width: 100;
  position: relative;
  height: 400px;
}
.image-container img {
  width: 100%;
}
.image-container .slider-title {
  position: absolute;
  bottom: 25%;
  display: block;
  width: 100%;
}
.image-container .slider-title .sub-title,
.image-container .slider-title .main-title {
  color: #fff;
  text-transform: uppercase;
  font-family: "Lato", "Arial", sans-serif;
  font-size: 48px;
  text-align: center;
  font-weight: 700;
  display: block;
  width: 80%;
  margin: auto;
  line-height: 0.9;
  cursor: pointer;
  transition: 0.4s;
}
.image-container .slider-title .main-title:focus,
.image-container .slider-title .main-title:hover {
  color: #e41f43;
}
.image-container .slider-title .sub-title {
  padding-top: 16px;
  color: #e41f43;
  font-size: 14px;
  font-weight: 400;
}
@media only screen and (max-width: 798px) {
  .slider-container {
    height: 240px !important;
  }
  .image-container .slider-title .main-title {
    font-size: 28px;
  }
  .image-container .slider-title .sub-title{
    font-size: 12px;
  }
  .image-container .slider-title{
    bottom:55%
  }

  
}
</style>
