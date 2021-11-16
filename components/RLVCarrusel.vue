<template>
     <div>
    <b-carousel
      id="carousel-1"
      v-model="slide"
      :interval="4000"
      controls
      indicators
      @sliding-start="onSlideStart"
      @sliding-end="onSlideEnd"
    >
    <b-carousel-slide>
      <template #img>
     <img
            class="d-block img-fluid w-100"
            :src="require('../static/img/distribuidor/slide1.png')"
            alt="image slot"
          ></template></b-carousel-slide>
    <b-carousel-slide> <template #img>
     <img
            class="d-block img-fluid w-100"
            :src="require('../static/img/distribuidor/slide2.png')"
            alt="image slot"
          ></template></b-carousel-slide>
    <b-carousel-slide> <template #img>
     <img
            class="d-block img-fluid w-100"
            :src="require('../static/img/distribuidor/slide3.png')"
            alt="image slot"
          ></template></b-carousel-slide>
    </b-carousel>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        slide: 0,
        sliding: null
      }
    },
    methods: {
      onSlideStart(slide) {
        this.sliding = true
      },
      onSlideEnd(slide) {
        this.sliding = false
      }
    }
  }
</script>