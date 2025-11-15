<script setup>
import TestimonialSlider from './TestimonialSlider.vue'

// Дані відгуків
const testimonials = [
  { id: 1, name: 'Ben Yardley', location: 'Київ - Кишинів', date: '1 May 2023', text: 'Lorem ipsum dolor sit amet...', rating: 5, avatar: reviewsPhoto1 },
  { id: 2, name: 'Craig Martin', location: 'Львів - Париж', date: '1 May 2023', text: 'Duis aute irure dolor in reprehenderit...', rating: 5, avatar: reviewsPhoto2 },
  { id: 3, name: 'Anna Petrova', location: 'Одеса - Варшава', date: '28 Apr 2023', text: 'Nemo enim ipsam voluptatem quia...', rating: 4, avatar: 'https://i.pravatar.cc/100?img=5' },
  { id: 4, name: 'Olegs Koval', location: 'Харків - Берлін', date: '25 Apr 2023', text: 'Neque porro quisquam est...', rating: 5, avatar: 'https://i.pravatar.cc/100?img=8' },
]

import reviewsPhoto1 from '/img/reviews-photo1.png'
import reviewsPhoto2 from '/img/reviews-photo2.png'
</script>
<template>
        <section class="profile__reviews">
      <div class="container">
        <div class="reviews__wrapp">
          <div class="reviews__left">
            <h2>Що <span>кажуть люди?</span></h2>
            <p>
              Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor
              incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud
              exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
            </p>
            <a href="#">Залишити відгук</a>
          </div>
          <div class="reviews__right">
            <TestimonialSlider :data="testimonials" />
          </div>
        </div>
      </div>
    </section>
</template>