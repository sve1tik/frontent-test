<script setup>
import { ref, watch } from 'vue'

const isMenuOpen = ref(false)

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value
}

const closeMenu = () => {
  isMenuOpen.value = false
}

watch(isMenuOpen, (newValue) => {
  if (newValue) {
    document.body.style.overflow = 'hidden'
  } else {
    document.body.style.overflow = ''
  }
})
</script>

<template>
  <header>
    <div class="container">
      <nav class="header__nav">
        <div class="nav__wrapper">
          <a href="#"><img src="/img/Logo.svg" alt="logo" class="nav__logo" /></a>
          <button
            class="nav__burger"
            @click="toggleMenu"
            :class="{ active: isMenuOpen }"
            aria-label="Меню"
          >
            <span></span>
            <span></span>
            <span></span>
          </button>
          <div class="nav__overlay" :class="{ active: isMenuOpen }" @click="closeMenu"></div>
          <div class="nav__menu" :class="{ active: isMenuOpen }">
            <ul class="nav__list">
              <li><a href="#" class="nav__link" @click="closeMenu">Головна</a></li>
              <li><a href="#" class="nav__link" @click="closeMenu">Перевізник</a></li>
              <li><a href="#" class="nav__link" @click="closeMenu">Про нас</a></li>
              <li>
                <a href="#" class="nav__link active" @click="closeMenu">Профіль перевізника</a>
              </li>
            </ul>
            <div class="nav__btn">
              <a href="#" class="nav__btn-create" @click="closeMenu">Створити профіль</a>
              <hr />
              <a href="#" class="nav__btn-login" @click="closeMenu">Увійти</a>
            </div>
          </div>
        </div>
      </nav>
    </div>
  </header>
</template>

<style>
.header__nav {
  padding: 15px 0;
}

.nav__wrapper {
  display: flex;
  max-width: 1280px;
  align-items: center;
}
.nav__logo {
  width: 160px;
  height: 48px;
  margin-right: 5rem;
}
.nav__list {
  display: flex;
  gap: 20px;
}

.nav__list li a {
  color: #515b6f;
  font-size: 16px;
  font-weight: 600;
}

.nav__btn {
  display: flex;
  gap: 20px;
  margin-left: auto;
}
.nav__btn a {
  font-size: 16px;
  font-weight: 700;
  text-align: center;
}
.nav__btn-create {
  color: #4640de;
  padding: 12px 24px;
  transition: all 0.2s ease;
}
.nav__btn-create:hover {
  opacity: 0.8;
}
.nav__btn-login {
  background: #4640de;
  color: white;
  padding: 12px 24px;
  transition: all 0.2s ease-in-out;
  border: 1px solid #4640de;
}
.nav__btn-login:hover {
  background: white;
  color: #4640de;
}
hr {
  border-color: #d6ddeb;
  margin: -1px 0;
}
.nav__link.active {
  color: #4640de;
  border-bottom: 4px solid #4640de;
  padding-bottom: 26px;
  transition: all 0.3s ease;
}

.nav__link:hover {
  color: #4640de;
}
/* Гамбургер-меню */
.nav__burger {
  display: none;
  flex-direction: column;
  justify-content: space-around;
  width: 30px;
  height: 30px;
  background: transparent;
  border: none;
  cursor: pointer;
  padding: 0;
  z-index: 1001;
  position: relative;
}

.nav__burger span {
  width: 100%;
  height: 3px;
  background-color: #25324b;
  border-radius: 3px;
  transition: all 0.3s ease;
  transform-origin: center;
}

.nav__burger.active span:nth-child(1) {
  transform: rotate(45deg) translate(8px, 8px);
}

.nav__burger.active span:nth-child(2) {
  opacity: 0;
}

.nav__burger.active span:nth-child(3) {
  transform: rotate(-45deg) translate(7px, -7px);
}

.nav__menu {
  display: flex;
  align-items: center;
  gap: 20px;
  flex: 1;
}
@media (max-width: 1200px) {
  .nav__logo {
    margin-right: 3rem;
  }
}

@media (min-width: 993px) {
  .nav__overlay {
    display: none !important;
  }
}

@media (max-width: 992px) {
  .nav__menu {
    position: fixed;
    top: 0;
    right: -100%;
    width: 100%;
    max-width: 400px;
    height: 100vh;
    background: white;
    flex-direction: column;
    align-items: flex-start;
    padding: 80px 30px 30px;
    box-shadow: -2px 0 10px rgba(0, 0, 0, 0.1);
    transition: right 0.3s ease;
    z-index: 1000;
    gap: 0;
  }

  .nav__list {
    flex-direction: column;
    width: 100%;
    gap: 0;
    margin-bottom: 30px;
  }
  .nav__menu.active {
    right: 0;
  }


  .nav__list li {
    width: 100%;
    border-bottom: 1px solid #e5e7eb;
  }

  .nav__list li a {
    display: block;
    padding: 15px 0;
    width: 100%;
  }

  .nav__link.active {
    border-bottom: none;
    padding-bottom: 15px;
    border-left: 4px solid #4640de;
    padding-left: 15px;
  }

  .nav__btn {
    flex-direction: column;
    width: 100%;
    margin-left: 0;
    gap: 15px;
  }

  .nav__btn hr {
    display: none;
  }

  .nav__btn a {
    width: 100%;
    text-align: center;
  }

  .nav__burger {
    display: flex;
    margin-left: auto;
  }

  .nav__overlay {
    display: none;
  }

  .nav__overlay.active {
    display: block;
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100vh;
    background: rgba(0, 0, 0, 0.5);
    z-index: 999;
    transition: opacity 0.3s ease;
  }
}

@media (max-width: 768px) {
  .header__nav {
    padding: 12px 0;
  }

  .nav__logo {
    width: 120px;
    height: 36px;
    margin-right: auto;
  }
}

@media (max-width: 480px) {
  .nav__logo {
    width: 100px;
    height: 30px;
  }
  .nav__menu {
    max-width: 100%;
    padding: 70px 20px 20px;
  }
}
</style>
