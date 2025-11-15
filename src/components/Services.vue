<script setup>
const props = defineProps({
  data: {
    type: Array,
    required: true,
  },
})
</script>
<template>
  <div v-if="data" class="services__wrapp">
    <div class="services__body" v-for="item in data" :key="item.id">
      <img :src="item.src" :alt="item.name" />
      <h4>{{ item.name }}</h4>
    </div>
  </div>
</template>

<style scoped>
.services__wrapp {
  display: flex;
  flex-wrap: wrap;
  gap: 32px;
}
.services__body {
  display: flex;
  gap: 12px;
  align-items: center;
}
.services__body h4 {
  color: #25324b;
  font-weight: 800;
  font-size: 24px;
}
.services__body:nth-child(5) h4,
.services__body:nth-child(6) h4 {
  width: 110px;
}
@media (max-width: 768px) {
  .services__wrapp {
    gap: 20px;
  }
  .services__body {
    gap: 10px;
  }
  .services__body h4 {
    font-size: 18px;
  }
}
</style>