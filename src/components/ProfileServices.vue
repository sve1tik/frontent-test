<script setup>
import Services from './Services.vue'

// Імпорт іконок і зображень
import modeFanIcon from '/img/mode_fan.svg'
import wifiIcon from '/img/wifi.svg'
import tvIcon from '/img/tv.svg'
import wcIcon from '/img/wc.svg'
import weekendIcon from '/img/weekend.svg'
import careIcon from '/img/care.svg'

// Дані для сервісів
const servicesInfo = [
  { id: 0, src: modeFanIcon, name: 'Кондиціонер' },
  { id: 1, src: wifiIcon, name: 'WI-FI' },
  { id: 2, src: tvIcon, name: 'TV' },
  { id: 3, src: wcIcon, name: 'Туалет' },
  { id: 4, src: weekendIcon, name: 'Зручні сидіння' },
  { id: 5, src: careIcon, name: 'Перевозимо тварин' },
]

</script>
<template>
        <section class="profile__services">
      <div class="container">
        <h3>Сервіс</h3>
        <p>Найкращі умови для вашого комфорту</p>
        <Services :data="servicesInfo" />
      </div>
    </section>
</template>

<style scoped>

.profile__services {
  padding-top: 72px;
  padding-bottom: 100px;
}
.profile__services h3 {
  color: #25324b;
  font-weight: 800;
  font-size: 32px;
}
.profile__services p {
  color: #515b6f;
  font-weight: 400;
  font-size: 16px;
  padding-bottom: 24px;
  padding-top: 8px;
}
@media (max-width: 768px) {
  .profile__services {
    padding-top: 50px;
    padding-bottom: 70px;
  }
  .profile__services h3 {
    font-size: 24px;
  }
  .profile__services p {
    font-size: 14px;
  }
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

@media (max-width: 480px) {
  .profile__services h3,
  .profile__services p {
    font-size: 20px;
  }
}
</style>