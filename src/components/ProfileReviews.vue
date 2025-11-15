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
<style scoped>
.reviews__wrapp {
  display: flex;
  justify-content: space-between;
}
.reviews__left h2 {
  color: #222222;
  font-weight: 800;
  font-size: 48px;
}
.reviews__left h2 span {
  color: #26a4ff;
}
.reviews__left p {
  color: #25324b;
  font-weight: 400;
  font-size: 16px;
  padding-top: 22px;
  padding-bottom: 42px;
  max-width: 422px;
}
.reviews__left a {
  color: white;
  background: #4640de;
  padding: 13px 28px;
  text-align: center;
  transition: all 0.2s ease;
  border: 1px solid #4640de;
}
.reviews__left a:hover {
  background: white;
  color: #4640de;
}
.profile__reviews {
  background-color: #f8f8fd;
  padding-top: 75px;
  padding-bottom: 45px;
  background-image:
    url('/img/reviews-line-right-up.svg'),
    url('/img/reviews-line-right-down.svg');
  background-repeat: no-repeat;
  background-position:
    right top,
    right bottom;
  background-size: 420px, 500px;
}
@media (max-width: 992px) {
  .reviews__wrapp {
    flex-direction: column;
    gap: 40px;
  }

  .reviews__left h2 {
    font-size: 36px;
  }

  .reviews__left p {
    max-width: 100%;
  }
}

@media (max-width: 768px) {
  .reviews__left h2 {
    font-size: 28px;
  }
  .reviews__left p {
    font-size: 14px;
    padding-top: 15px;
    padding-bottom: 30px;
  }
  .reviews__left a {
    padding: 12px 24px;
    font-size: 14px;
  }
}

@media (max-width: 480px) {
  .reviews__left h2 {
    font-size: 24px;
  }
  .reviews__left p {
    font-size: 13px;
  }
}
</style>
