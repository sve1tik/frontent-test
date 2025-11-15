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
  <footer>
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
<style scoped>

footer {
  background-color: #202430;
  color: #d6ddeb;
  padding: 4rem 0 2rem 0;
  font-size: 0.95rem;
}
.footer-top {
  display: grid;
  grid-template-columns: 1.5fr 1fr 1fr 1.5fr;
  gap: 2rem;
}

.footer-column h3 {
  color: #ffffff;
  font-size: 1.1rem;
  font-weight: 600;
  margin-bottom: 1.25rem;
}

.footer-column.about p {
  line-height: 1.6;
  margin-top: 1rem;
}

.footer-column.links ul {
  list-style: none;
  padding: 0;
  margin: 0;
}
.footer-column.links li {
  margin-bottom: 0.75rem;
}
.footer-column.links a {
  color: #a0aec0;
  text-decoration: none;
  transition: color 0.2s ease;
}
.footer-column.links a:hover {
  color: #ffffff;
}

.footer-column.contact p {
  margin-bottom: 1rem;
}
.subscribe-form {
  display: flex;
  margin-bottom: 1rem;
  gap: 5px;
  flex-wrap: wrap;
  justify-content: center;
  max-width: 350px;
}
.subscribe-form input {
  flex-grow: 1;
  border: none;
  padding: 12px 16px;
  background-color: #ffffff;
  color: #333;
}
.subscribe-form button {
  border: none;
  background-color: #4640de;
  color: white;
  padding: 12px 24px;
  cursor: pointer;
  font-weight: 700;
  transition: all 0.2s ease-in-out;
  border: 1px solid #4640de;
}
.subscribe-form button:hover {
  background-color: white;
  color: #4640de;
}
.contact-info a {
  display: flex;
  align-items: center;
  color: #a0aec0;
  text-decoration: none;
  margin-bottom: 0.5rem;
}
.contact-info a img {
  margin-right: 0.5rem;
}
.contact-info a:hover {
  color: #ffffff;
}
.footer-divider {
  border: 0;
  border-top: 1px solid #3e4c63;
  margin: 3rem 0;
}
.footer-bottom {
  display: flex;
  justify-content: space-between;
  align-items: center;
  color: #a0aec0;
}

.social-icons {
  display: flex;
  gap: 0.75rem;
}
.social-icons a {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 36px;
  height: 36px;
  border-radius: 50%;
  background-color: #3e4c63;
  color: #ffffff;
  text-decoration: none;
  font-weight: 600;
  transition: background-color 0.2s ease;
}
.social-icons a:hover {
  background-color: #5a3eaa;
}
@media (max-width: 992px) {
  .footer-top {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (max-width: 768px) {
  .footer-top {
    grid-template-columns: 1fr;
  }
  .footer-bottom {
    flex-direction: column-reverse;
    gap: 1.5rem;
  }
  .social-icons {
    margin-top: 1rem;
  }
}
@media (max-width: 480px) {
  .subscribe-form {
    flex-direction: column;
  }
  .subscribe-form input,
  .subscribe-form button {
    width: 100%;
  }
}
</style>
