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
