<script setup>
const props = defineProps({
  data: {
    type: Array,
    required: true,
  },
})
</script>
<template>
  <div class="bus-info" v-if="data">
    <div v-for="item in data" :key="item.id" class="bus-info__item">
      <div class="bus-info__icon">
        <img :src="item.icon" alt="icon" />
      </div>
      <div class="bus-info__content">
        <h3>{{ item.title }}</h3>
        <p>{{ item.description }}</p>
      </div>
    </div>
  </div>
</template>
<style scoped>
.bus-info {
  display: flex;
  align-items: center;
  gap: 32px;
  flex-wrap: wrap;
}
.bus-info__item {
  display: flex;
  align-items: center;
  gap: 16px;
}
.bus-info__icon {
  padding: 8px 10px;
  border-radius: 50%;
  background: white;
  display: flex;
  align-items: center;
}
.bus-info__icon img {
  width: 24px;
  height: 24px;
}
.bus-info__content {
  display: grid;
  gap: 10px;
}
.bus-info__content h3 {
  font-size: 16px;
  font-weight: 400;
  color: #515b6f;
}
.bus-info__content p {
  font-size: 14px;
  font-weight: 600;
  color: #25324b;
}
@media (max-width: 992px) {
  .bus-info {
    gap: 20px;
    justify-content: unset;
  }
}

@media (max-width: 768px) {
  .bus-info {
    flex-direction: column;
    gap: 16px;
    align-items: flex-start;
  }
  .bus-info__item {
    width: 100%;
  }
}

@media (max-width: 480px) {
  .bus-info__content h3 {
    font-size: 18px;
  }
  .bus-info__content p {
    font-size: 16px;
  }
}
</style>