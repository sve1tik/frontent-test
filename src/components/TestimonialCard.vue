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

<style scoped>


.testimonial-card {
  background: #ffffff;
  border-radius: 12px;
  padding: 1.5rem;
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.05);
  height: 100%;
  display: flex;
  flex-direction: column;
}

.card-header {
  display: flex;
  align-items: center;
  margin-bottom: 1rem;
}

.avatar {
  width: 50px;
  height: 50px;
  border-radius: 50%;
  margin-right: 1rem;
  object-fit: cover;
}

.info {
  display: grid;
  gap: 5px;
}

.name {
  font-weight: 600;
  color: #25324b;
  font-size: 24px;
}

@media (max-width: 768px) {
  .testimonial-card {
    padding: 1rem;
  }

  .name {
    font-size: 20px;
  }

  .text {
    font-size: 14px;
  }

  .avatar {
    width: 40px;
    height: 40px;
  }
}

.location {
  color: #4640de;
  font-size: 14px;
}
.date {
  color: #6c757d;
  font-size: 14px;
}

.text {
  font-size: 16px;
  color: #4a5568;
  margin-bottom: 1rem;
  flex-grow: 1;
}

.rating .star {
  font-size: 1.25rem;
  color: #e0e0e0;
}

.rating .star.filled {
  color: #5a3eaa;
}

</style>

