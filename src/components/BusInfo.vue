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
<style scoped></style>
