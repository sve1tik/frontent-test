<template>
  <div class="slider-container">
    <swiper
      :modules="[Pagination]"
      :slides-per-view="2"
      :space-between="30"
      :pagination="{ clickable: true }"
      :breakpoints="{
        '320': {
          slidesPerView: 1,
          spaceBetween: 15,
        },
        '768': {
          slidesPerView: 2,
          spaceBetween: 30,
        },
      }"
      class="my-testimonial-swiper"
    >
      <swiper-slide v-for="item in data" :key="item.id">
        <TestimonialCard :testimonial="item" />
      </swiper-slide>
    </swiper>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import { Swiper, SwiperSlide } from 'swiper/vue'
import { Pagination } from 'swiper/modules'

import 'swiper/css'
import 'swiper/css/pagination'

import TestimonialCard from './TestimonialCard.vue'

const props = defineProps({
  data: {
    type: Array,
    required: true,
  },
})
</script>

<style scoped>
.slider-container {
  width: 600px;
  max-width: 100%;
}
.my-testimonial-swiper {
  padding-bottom: 50px !important;
}

.my-testimonial-swiper .swiper-pagination-bullet {
  width: 10px;
  height: 10px;
  background-color: #d6d6d6;
  opacity: 1;
  transition: all 0.3s ease;
}

.my-testimonial-swiper .swiper-pagination-bullet-active {
  background-color: #5a3eaa;
  width: 25px;
  border-radius: 5px;
}

@media (max-width: 992px) {
  .slider-container {
    width: 100%;
  }
}

</style>
