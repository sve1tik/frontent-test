<script setup>
import BusInfo from './BusInfo.vue'
import busImg from '/img/bus.png'
import fireIcon from '/img/fire.svg'
import peoplesIcon from '/img/peoples.svg'
import trainIcon from '/img/train.svg'
import mapIcon from '/img/map.svg'
import cityIcon from '/img/city.svg'
// Дані про автобус
const busInfo = [
  { id: 0, icon: fireIcon, title: 'На ринку від', description: 'Травень 31, 2011' },
  { id: 1, icon: peoplesIcon, title: 'Перевезених пасажирів', description: '4000+' },
  { id: 2, icon: trainIcon, title: 'Автопарк', description: '8 бусів' },
  { id: 3, icon: mapIcon, title: 'Обслуговуємо', description: '8 країн' },
  { id: 4, icon: cityIcon, title: 'Місто', description: 'Львів' },
]

</script>
<template>
        <section class="profile-header">
      <div class="container">
        <nav>
          <ol class="profile__bread-crumbs">
            <li><a href="#">Головна</a></li>
            <li><a href="#">Перевізник</a></li>
            <li><a href="#">Про нас</a></li>
            <li><a href="#">Профіль перевізника</a></li>
          </ol>
          <div class="profile__info">
            <div class="profile__info-wrapper">
              <div class="content__left">
                <img :src="busImg" alt="profile" />
              </div>
              <div class="content__right">
                <div class="content__title">
                  <h2>Stripe</h2>
                  <span>43 Поїздок</span>
                </div>
                <div class="content__callback">
                  <a href="https://stripe.com" target="_blank">https://stripe.com</a>
                  <a href="tel:+380735555555" target="_blank">+38 (073) 555 55 55</a>
                </div>
                <div class="content__description">
                  <BusInfo :data="busInfo" />
                </div>
              </div>
            </div>
          </div>
        </nav>
      </div>
    </section>
</template>