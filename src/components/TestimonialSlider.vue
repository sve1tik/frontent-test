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
