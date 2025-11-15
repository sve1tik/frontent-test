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