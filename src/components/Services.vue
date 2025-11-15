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
