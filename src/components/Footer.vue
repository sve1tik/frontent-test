<script setup>
import { ref } from 'vue'
const clientLinks = ref([
  { text: 'Головна', path: '#' },
  { text: 'Про нас', path: '#' },
  { text: 'Ціни', path: '#' },
  { text: 'Маршрути', path: '#' },
  { text: 'Політика приватності', path: '#' },
])

const carrierLinks = ref([
  { text: 'Help Docs', path: '#' },
  { text: 'Особистий кабінет', path: '#' },
  { text: 'Оновлення', path: '#' },
  { text: 'Контакти', path: '#' },
])

const handleSubmit = () => {
  alert('Форма відправлена!')
}
</script>
<template>
  <footer class="site-footer">
    <div class="container">
      <div class="footer-top">
        <div class="footer-column about">
          <img src="/img/logo-footer.svg" alt="" />
          <p>Платформа пошуку перевізників та бронювання поїздок</p>
        </div>

        <div class="footer-column links">
          <h3>Клієнтам</h3>
          <ul>
            <li v-for="link in clientLinks" :key="link.text">
              <a :href="link.path">{{ link.text }}</a>
            </li>
          </ul>
        </div>

        <div class="footer-column links">
          <h3>Перевізникам</h3>
          <ul>
            <li v-for="link in carrierLinks" :key="link.text">
              <a :href="link.path">{{ link.text }}</a>
            </li>
          </ul>
        </div>

        <div class="footer-column contact">
          <h3>Зворотній зв'язок</h3>
          <p>Маєш пропозиції щодо покращення сервісу - пиши нам!</p>
          <form @submit.prevent="handleSubmit" class="subscribe-form">
            <input type="email" placeholder="Email Address" required />
            <button type="submit">Надіслати</button>
          </form>
          <div class="contact-info">
            <a href="tel:+380735555555">
              <img src="/img/tel.svg" alt="tel" />
              +38 (073) 555 55 55
            </a>
            <a href="mailto:gmail@gmail.com">
              <img src="/img/gmail.svg" alt="gmail" />
              gmail@gmail.com
            </a>
          </div>
        </div>
      </div>

      <hr class="footer-divider" />

      <div class="footer-bottom">
        <span class="copyright">2024 @ Sprinters. All rights reserved.</span>

        <div class="social-icons">
          <a href="#" aria-label="Facebook"
            ><img src="/img/facebook2.svg" alt="Facebook2"
          /></a>
          <a href="#" aria-label="Instagram"
            ><img src="/img/instagram2.svg" alt="Instagram2"
          /></a>
          <a href="#" aria-label="Dribbble"
            ><img src="/img/dribbble.svg" alt="Dribbble"
          /></a>
          <a href="#" aria-label="LinkedIn"
            ><img src="/img/linkedin2.svg" alt="LinkedIn"
          /></a>
          <a href="#" aria-label="Twitter"><img src="/img/twitter.svg" alt="Twitter" /></a>
        </div>
      </div>
    </div>
  </footer>
</template>
