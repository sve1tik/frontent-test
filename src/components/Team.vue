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

<style scoped>

.team__body {
  display: grid;
  gap: 16px;
  border: 1px solid #d6ddeb;
  padding: 24px;
  align-items: center;
  width: fit-content;
  margin-inline: auto;
}
.team__img {
  margin: 0 auto;
}
.team__body h4 {
  color: #25324b;
  font-size: 18px;
  font-weight: 600;
  text-align: center;
}
.team__body p {
  color: #7c8493;
  font-weight: 400;
  font-size: 16px;
  text-align: center;
}
.team__body:nth-child(2) {
  display: grid;
  gap: 4px;
}
.team__wrapp {
  display: flex;
  gap: 20px;
  padding-bottom: 75px;
  border-bottom: 1px solid #d6ddeb;
}
.team__social {
  display: flex;
  justify-content: center;
  gap: 30px;
}
@media (max-width: 992px) {
  .team__wrapp {
    flex-direction: column;
    gap: 20px;
  }
}

@media (max-width: 768px) {
  .team__body {
    padding: 20px;
  }
}
</style>