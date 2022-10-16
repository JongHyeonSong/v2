<script setup lang="ts">
import { onActivated, onMounted } from "vue";
import { Navigation, Pagination, Scrollbar, Autoplay, A11y } from "swiper";
import type { Swiper as SwiperType } from "swiper";

// Import Swiper Vue.js components
import { Swiper, SwiperSlide } from "swiper/vue";

// Import Swiper styles
import "swiper/css";
import "swiper/css/navigation";
import "swiper/css/pagination";
import "swiper/css/scrollbar";

onMounted(() => {
  console.log("🚀 ~ onMounted ~ onMounted");
});

onActivated(() => {
  console.log("🚀 ~ onActivated ~ onActivated", onActivated);
});

const onSwiper = (swiper: SwiperType) => {
  console.log(swiper);
};
const onSlideChange = () => {
  console.log("slide change");
};
</script>

<template>
  <main>
    <!-- <TheWelcome /> -->
    <h3>im main</h3>

    <swiper
      :loop="true"
      :modules="[Navigation, Pagination, Scrollbar, A11y, Autoplay]"
      :slides-per-view="1"
      :space-between="50"
      :autoplay="{ delay: 500, disableOnInteraction: false }"
      navigation
      :pagination="{ clickable: true }"
      :scrollbar="{ draggable: true }"
      @swiper="onSwiper"
      @slideChange="onSlideChange"
    >
      <swiper-slide><p class="pp">slide1</p></swiper-slide>
      <swiper-slide><p class="pp">slide2</p></swiper-slide>
      <swiper-slide><p class="pp">slide3</p></swiper-slide>
      <swiper-slide><p class="pp">slide4</p></swiper-slide>
      <swiper-slide><p class="pp">slide5</p></swiper-slide>
      <swiper-slide><p class="pp">slide6</p></swiper-slide>
      <swiper-slide><p class="pp">slide7</p></swiper-slide>
      <swiper-slide><p class="pp">slide8</p></swiper-slide>
      ...
    </swiper>
  </main>
</template>

<style>
p {
  background-color: pink;
  width: 200px;
  height: 565px;
  color: black;
}
</style>
