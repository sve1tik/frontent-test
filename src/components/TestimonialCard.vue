<template>
  <div class="testimonial-card">
    <div class="card-header">
      <img :src="testimonial.avatar" alt="avatar" class="avatar" />
      <div class="info">
        <div class="name">{{ testimonial.name }}</div>
        <div class="location">{{ testimonial.location }}</div>
        <div class="date">{{ testimonial.date }}</div>
      </div>
    </div>
    <p class="text">{{ testimonial.text }}</p>
    <div class="rating">
      <span v-for="n in 5" :key="n" class="star" :class="{ filled: n <= testimonial.rating }">
        &#9733;
      </span>
    </div>
  </div>
</template>

<script setup>
defineProps({
  testimonial: {
    type: Object,
    required: true,
  },
})
</script>
