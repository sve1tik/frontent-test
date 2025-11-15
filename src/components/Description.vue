<script setup>
import car1Img from '/img/car1.png'
import car2Img from '/img/car2.png'
import car3Img from '/img/car3.png'
import bird from '/img/bird.svg'
import facebook from '/img/facebook.svg'
import franceSvg from '/img/France.svg'
import italySvg from '/img/Italy.svg'
import germanySvg from '/img/Germany.svg'
import netherlandsSvg from '/img/Netherlands.svg'
import spainSvg from '/img/Spain.svg'
// Імпорт стилів
import 'v-calendar/dist/style.css'

import { Calendar as VCalendar } from 'v-calendar'

import Country from './Country.vue'


// Дані для країн
const countryInfo = [
  { id: 0, name: 'Франція', src: franceSvg },
  { id: 1, name: 'Італія', src: italySvg },
  { id: 2, name: 'Німеччина', src: germanySvg },
  { id: 3, name: 'Нідерланди', src: netherlandsSvg },
  { id: 4, name: 'Іспанія', src: spainSvg },
]

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

const attributes = [
  { key: 'tripDates', highlight: { color: '#4640DE', fillMode: 'solid' }, dates: datesForTrips }
]
</script>
<template>
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
                <a href="https://twitter.com/stripe" target="_blank"><img :src="bird" alt="bird">twitter.com/stripe</a>
                <a href="https://facebook.com/StripeHQ" target="_blank"><img :src="facebook" alt="bird">facebook.com/StripeHQ</a>
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
</template>

<style scoped>

.profile__main {
  padding-top: 178px;
  padding-bottom: 144px;
}
.profile__wrapper {
  display: grid;
  grid-template-columns: 2fr 1fr;
  gap: 2rem;
}

.profile__article {
  max-width: 752px;
}
.profile__description {
  display: grid;
  gap: 16px;
}
.profile__description h3,
.profile__social h3,
.profile__calendar h3 {
  color: #25324b;
  font-size: 32px;
  font-weight: 800px;
}
.profile__description p {
  color: #515b6f;
  font-size: 16px;
  font-weight: 400;
  padding-bottom: 24px;
}
.profile__social > span {
  display: flex;
  gap: 30px;
  padding-top: 16px;
}
.profile__social > span > a {
  border: 1px solid #4640de;
  position: relative;
  padding: 15px 30px;
  color: #4640de;
  align-items: center;
  display: inline-flex;
  gap: 8px;
  transition: all 0.2s ease;
}
.profile__social > span > a:hover{
  opacity: 0.8;
}
.profile__gallery {
  padding-top: 40px;
}

.profile__gallery div {
  display: grid;
  gap: 20px;
}

.profile__gallery img {
  width: 100%;
  height: auto;
  border-radius: 8px;
  object-fit: cover;
}
.profile__countries {
  border-bottom: 1px solid #d6ddeb;
  padding-bottom: 24px;
}
.profile__countries a {
  color: #4640de;
  font-size: 16px;
  font-weight: 600;
  position: relative;
  padding-right: 16px;
  transition: all 0.2s ease;
}
.profile__countries a:hover {
  opacity: 0.8;
}
.profile__countries a::after {
  content: '';
  position: absolute;
  top: 5px;
  right: -16px;
  width: 24px;
  height: 24px;
  background-image: url('/img/arrow-down.svg');
  background-repeat: no-repeat;
  background-size: 14px;
}
.profile__calendar {
  padding-top: 64px;
}
.profile__calendar h3 {
  margin-bottom: 24px;
}
.profile__calendar a {
  padding: 12px 16px;
  border: 1px solid #ccccf5;
  color: #4640de;
  text-align: center;
  position: relative;
  transition: all 0.2s ease-in-out;
}
.profile__calendar a:hover {
  color: #ccccf5;
  border: 1px solid #4640de;
  background: #4640de;
}
.profile__calendar a::after {
  content: '+';
  position: absolute;
  width: 20px;
  height: 20px;
  top: 10px;
  left: 30px;
  font-size: 20px;
}
.profile__calendar-wrapp {
  padding: 24px 24px 24px 32px;
  border: 1px solid #d6ddeb;
  display: grid;
  gap: 20px;
  justify-content: center;

}
.vc-bordered {
  border: none;
}

@media (max-width: 992px) {
  .profile__main {
    padding-top: 100px;
    padding-bottom: 80px;
  }
  .profile__wrapper {
    grid-template-columns: 1fr;
    gap: 3rem;
  }
  .profile__gallery div {
    gap: 15px;
  }
  .profile__calendar-wrapp{
    width: fit-content;
    margin-inline: auto;
  }
}

@media (max-width: 768px) {
  .profile__main {
    padding-top: 60px;
    padding-bottom: 60px;
  }
  .profile__gallery div {
    grid-template-columns: 1fr;
    gap: 15px;
  }
  .profile__gallery img {
    width: 100%;
    height: auto;
    margin-bottom: 0;
  }
  .profile__description h3,
  .profile__social h3,
  .profile__calendar h3 {
    font-size: 24px;
  }
  .profile__description p {
    font-size: 14px;
  }
  .profile__social > span {
    gap: 15px;
    flex-direction: column;
  }
  .profile__social > span > a {
    width: 100%;
    text-align: center;
  }
  .profile__gallery {
    padding-top: 30px;
  }
  .profile__gallery div {
    grid-template-columns: 1fr;
    gap: 15px;
  }
  .profile__gallery img {
    width: 100%;
    height: auto;
    margin-bottom: 0;
  }
  .profile__countries {
    padding-bottom: 20px;
  }
  .profile__calendar {
    padding-top: 40px;
  }
  .profile__calendar-wrapp {
    padding: 20px 15px;
  }
}

@media (max-width: 480px) {
  .container {
    padding: 0 10px;
  }
  .profile__description h3,
  .profile__social h3,
  .profile__calendar h3,
  .drivers__title h3,
  .profile__services h3 {
    font-size: 20px;
  }
  .profile__description p {
    font-size: 13px;
  }
}

</style>
