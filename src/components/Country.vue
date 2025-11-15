<script setup>
const props = defineProps({
  data: {
    type: Array,
    required: true,
  },
})
</script>

<template>
  <div class="country__body" v-if="data">
    <div class="country__block" v-for="item in data" :key="item.id">
      <img :src="item.src" :alt="item.name" />
      <p>{{ item.name }}</p>
    </div>
  </div>
</template>
<style scoped>
.country__block {
  display: flex;
  gap: 16px;
}
.country__body {
  display: grid;
  gap: 14px;
  padding-bottom: 34px;
  padding-top: 24px;
}
@media (max-width: 992px) {
  .country__body {
    display: flex;
    justify-content: space-between;
  }
}

@media (max-width: 768px) {
  .country__body {
    flex-wrap: wrap;
    gap: 12px;
    justify-content: unset;
  }
  .country__block {
    gap: 8px;
  }
}
</style>