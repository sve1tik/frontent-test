<script setup>
import Team from './Team.vue'
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