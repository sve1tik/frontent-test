<script setup>
// Імпорт компонентів
import BusInfo from './components/BusInfo.vue'
import Country from './components/Country.vue'
import Team from './components/Team.vue'
import Services from './components/Services.vue'
import TestimonialSlider from './components/TestimonialSlider.vue'
import TheFooter from './components/TheFooter.vue'
import TheHeader from './components/TheHeader.vue'

// Імпорт бібліотек
import { Calendar as VCalendar } from 'v-calendar'
import { ref } from 'vue'

// Імпорт стилів
import 'v-calendar/dist/style.css'

// Імпорт іконок і зображень
import modeFanIcon from '/img/mode_fan.svg'
import wifiIcon from '/img/wifi.svg'
import tvIcon from '/img/tv.svg'
import wcIcon from '/img/wc.svg'
import weekendIcon from '/img/weekend.svg'
import careIcon from '/img/care.svg'

import team1Img from '/img/team1.png'
import team2Img from '/img/team2.png'
import team3Img from '/img/team3.png'
import team4Img from '/img/team4.png'
import team5Img from '/img/team5.png'

import franceSvg from '/img/France.svg'
import italySvg from '/img/Italy.svg'
import germanySvg from '/img/Germany.svg'
import netherlandsSvg from '/img/Netherlands.svg'
import spainSvg from '/img/Spain.svg'

import fireIcon from '/img/fire.svg'
import peoplesIcon from '/img/peoples.svg'
import trainIcon from '/img/train.svg'
import mapIcon from '/img/map.svg'
import cityIcon from '/img/city.svg'

import busImg from '/img/bus.png'
import car1Img from '/img/car1.png'
import car2Img from '/img/car2.png'
import car3Img from '/img/car3.png'

import reviewsPhoto1 from '/img/reviews-photo1.png'
import reviewsPhoto2 from '/img/reviews-photo2.png'

// Дані для сервісів
const servicesInfo = [
  { id: 0, src: modeFanIcon, name: 'Кондиціонер' },
  { id: 1, src: wifiIcon, name: 'WI-FI' },
  { id: 2, src: tvIcon, name: 'TV' },
  { id: 3, src: wcIcon, name: 'Туалет' },
  { id: 4, src: weekendIcon, name: 'Зручні сидіння' },
  { id: 5, src: careIcon, name: 'Перевозимо тварин' },
]

// Дані для команди
const teamInfo = [
  { id: 0, name: 'Олександр', src: team1Img, description: 'Досвід роботи: 5 років' },
  { id: 1, name: 'Володимир', src: team2Img, description: 'Досвід роботи: 7 років' },
  { id: 2, name: 'Ірина', src: team3Img, description: 'Досвід роботи: 1 рік' },
  { id: 3, name: 'Михайло', src: team5Img, description: 'Досвід роботи: 1 рік' },
  { id: 4, name: 'Юлія', src: team4Img, description: 'Досвід роботи: 2 роки' },
]

// Дані для країн
const countryInfo = [
  { id: 0, name: 'Франція', src: franceSvg },
  { id: 1, name: 'Італія', src: italySvg },
  { id: 2, name: 'Німеччина', src: germanySvg },
  { id: 3, name: 'Нідерланди', src: netherlandsSvg },
  { id: 4, name: 'Іспанія', src: spainSvg },
]

// Дані про автобус
const busInfo = [
  { id: 0, icon: fireIcon, title: 'На ринку від', description: 'Травень 31, 2011' },
  { id: 1, icon: peoplesIcon, title: 'Перевезених пасажирів', description: '4000+' },
  { id: 2, icon: trainIcon, title: 'Автопарк', description: '8 бусів' },
  { id: 3, icon: mapIcon, title: 'Обслуговуємо', description: '8 країн' },
  { id: 4, icon: cityIcon, title: 'Місто', description: 'Львів' },
]

// Дані відгуків
const testimonials = ref([
  { id: 1, name: 'Ben Yardley', location: 'Київ - Кишинів', date: '1 May 2023', text: 'Lorem ipsum dolor sit amet...', rating: 5, avatar: reviewsPhoto1 },
  { id: 2, name: 'Craig Martin', location: 'Львів - Париж', date: '1 May 2023', text: 'Duis aute irure dolor in reprehenderit...', rating: 5, avatar: reviewsPhoto2 },
  { id: 3, name: 'Anna Petrova', location: 'Одеса - Варшава', date: '28 Apr 2023', text: 'Nemo enim ipsam voluptatem quia...', rating: 4, avatar: 'https://i.pravatar.cc/100?img=5' },
  { id: 4, name: 'Olegs Koval', location: 'Харків - Берлін', date: '25 Apr 2023', text: 'Neque porro quisquam est...', rating: 5, avatar: 'https://i.pravatar.cc/100?img=8' },
])

// Налаштування календаря
const now = new Date()
const currentYear = now.getFullYear()
const currentMonth = now.getMonth()
const datesForTrips = [
  new Date(currentYear, currentMonth, 2),
  new Date(currentYear, currentMonth, 4),
  new Date(currentYear, currentMonth, 20),
  new Date(currentYear, currentMonth, 24),
]

const attributes = ref([
  { key: 'tripDates', highlight: { color: '#4640DE', fillMode: 'solid' }, dates: datesForTrips }
])
</script>

<template>
  <TheHeader />
  <main>
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

    <section class="profile__main">
      <div class="container">
        <div class="profile__wrapper">
          <article class="profile__article">
            <section class="profile__description">
              <h3>Опис перевізника</h3>
              <p>
                Stripe is a software platform for starting and running internet businesses. Millions
                of businesses rely on Stripe's software tools to accept payments, expand globally,
                and manage their businesses online. Stripe has been at the forefront of expanding
                internet commerce, powering new business models, and supporting the latest
                platforms, from marketplaces to mobile commerce sites. We believe that growing the
                GDP of the internet is a problem rooted in code and design, not finance. Stripe is
                built for developers, makers, and creators. We work on solving the hard technical
                problems necessary to build global economic infrastructure—from designing highly
                reliable systems to developing advanced machine learning algorithms to prevent
                fraud.
              </p>
            </section>

            <section class="profile__social">
              <h3>Ми у соц. мережах</h3>
              <span>
                <a href="twitter.com/stripe" target="_blank">twitter.com/stripe</a>
                <a href="facebook.com/StripeHQ" target="_blank">facebook.com/StripeHQ</a>
              </span>
            </section>

            <section class="profile__gallery">
              <div>
                <img :src="car1Img" alt="Car1" />
                <img :src="car2Img" alt="Car2" />
                <img :src="car3Img" alt="Car3" />
              </div>
            </section>
          </article>

          <aside class="profile__aside">
            <section class="profile__countries">
              <h3>Обслуговуємо країни</h3>
              <Country :data="countryInfo" />
              <a href="#">Усі країни</a>
            </section>

            <section class="profile__calendar">
              <h3>Календар поїздок</h3>
              <div class="profile__calendar-wrapp">
                <a href="#">Купити квиток</a>
                <VCalendar :attributes="attributes" is-expanded locale="en-US" />
              </div>
            </section>
          </aside>
        </div>
      </div>
    </section>

    <section class="profile__team">
      <div class="container">
        <div class="drivers__title">
          <h3>Наші водії</h3>
          <a href="#">Усі водії (7)</a>
        </div>
        <Team :data="teamInfo" />
      </div>
    </section>

    <section class="profile__services">
      <div class="container">
        <h3>Сервіс</h3>
        <p>Найкращі умови для вашого комфорту</p>
        <Services :data="servicesInfo" />
      </div>
    </section>

    <section class="profile__reviews">
      <div class="container">
        <div class="reviews__wrapp">
          <div class="reviews__left">
            <h2>Що <span>кажуть люди?</span></h2>
            <p>
              Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor
              incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud
              exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
            </p>
            <a href="#">Залишити відгук</a>
          </div>
          <div class="reviews__right">
            <TestimonialSlider :data="testimonials" />
          </div>
        </div>
      </div>
    </section>
  </main>

  <TheFooter />
</template>