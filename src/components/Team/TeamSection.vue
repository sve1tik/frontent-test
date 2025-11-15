<script setup>
import Team from './TeamList.vue'
import team1Img from '/img/team1.png'
import team2Img from '/img/team2.png'
import team3Img from '/img/team3.png'
import team4Img from '/img/team4.png'
import team5Img from '/img/team5.png'

// Дані для команди
const teamInfo = [
  { id: 0, name: 'Олександр', src: team1Img, description: 'Досвід роботи: 5 років' },
  { id: 1, name: 'Володимир', src: team2Img, description: 'Досвід роботи: 7 років' },
  { id: 2, name: 'Ірина', src: team3Img, description: 'Досвід роботи: 1 рік' },
  { id: 3, name: 'Михайло', src: team5Img, description: 'Досвід роботи: 1 рік' },
  { id: 4, name: 'Юлія', src: team4Img, description: 'Досвід роботи: 2 роки' },
]

</script>
<template>
    <section class="profile__team">
      <div class="container">
        <div class="drivers__title">
          <h3>Наші водії</h3>
          <a href="#">Усі водії (7)</a>
        </div>
        <Team :data="teamInfo" />
      </div>
    </section>
</template>

<style scoped>
.drivers__title {
  display: flex;
  justify-content: space-between;
  padding-bottom: 11px;
}
.drivers__title a {
  color: #4640de;
  font-weight: 600;
  font-size: 16px;
  transition: all 0.2s ease;
}
.drivers__title a :hover {
  opacity: 0.8; 
}
.drivers__title h3 {
  color: #25324b;
  font-weight: 800;
  font-size: 32px;
}
@media (max-width: 768px) {
  .drivers__title {
    flex-direction: column;
    align-items: flex-start;
    gap: 15px;
  }
  .drivers__title h3 {
    font-size: 24px;
  }
  .team__wrapp {
    padding-bottom: 50px;
  }
}


</style>