<script setup>
const props = defineProps({
  data: {
    type: Array,
    required: true,
  },
})
</script>
<template>
  <div v-if="data" class="team__wrapp">
    <div v-for="item in data" :key="item.id" class="team__body">
      <div class="team__img"><img :src="item.src" :alt="item.name" /></div>
      <div>
        <h4>{{ item.name }}</h4>
        <p>{{ item.description }}</p>
      </div>
      <div class="team__social">
        <a href="#"><img src="/img/instagram.svg" alt="" /></a>
        <a href="#"><img src="/img/linkedin.svg" alt="" /></a>
      </div>
    </div>
  </div>
</template>
