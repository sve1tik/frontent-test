<script setup>
import car1Img from '/img/car1.png'
import car2Img from '/img/car2.png'
import car3Img from '/img/car3.png'

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
</template>