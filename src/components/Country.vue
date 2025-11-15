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
