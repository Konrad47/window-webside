<template>
  <div id="el">
    <div id="carousel">
      <b-carousel
        id="carousel-1"
        style="text-shadow: 0px 0px 2px #000"
        v-model="slide"
        controls
        background="#ababab"
        label-next
        label-prev
        indicators="true"
        label-indicators
        fade
        @sliding-start="onSlideStart"
        @sliding-end="onSlideEnd"
      >
        <!-- fade -->
        <b-carousel-slide
          style="
            background-image: url('https://picsum.photos/1024/480/?image=54');
          "
          caption="First Slide"
          :img-src="image1"
        ></b-carousel-slide>
        <b-carousel-slide
          caption="Second Slide"
          :img-src="image2"
        ></b-carousel-slide>
        <b-carousel-slide
          caption="Third Slide"
          :img-src="image3"
        ></b-carousel-slide>
      </b-carousel>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      slide: 0,
      sliding: null,
      image1: require("@/assets/asvgbBalustrada/AS_IGB_slupek-w-fasadzie_564_PL.jpg"),
      image2: require("@/assets/asvgbBalustrada/AS_VGB.jpg"),
      image3: require("@/assets/asvgbBalustrada/AS-IGB-slupek-jednoprofilowy_PL.png"),
    };
  },
  methods: {
    onSlideStart() {
      this.sliding = true;
    },
    onSlideEnd() {
      this.sliding = false;
    },
  },
};
</script>

<style scoped>
#el {
  padding-top: 20px;
  padding-bottom: 20px;
}
#carousel-1 {
  /* width: 90%; */
  width: 600px;
  margin: auto;
  box-shadow: 0 1em 1em gray;
}
</style>