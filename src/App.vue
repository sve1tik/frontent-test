<script setup>
// Імпорт компонентів
import Footer from './components/Footer.vue'
import Header from './components/Header.vue'
import Hero from './components/Hero.vue'
import Description from './components/Description.vue'
import Team from './components/Team/TeamSection.vue'
import Services from './components/Services/ServicesSection.vue'
import Reviews from './components/Reviews.vue'
</script>

<template>
  <Header />
  <main>
    <Hero />
    <Description />
    <Team />
    <Services />
    <Reviews />
  </main>
  <Footer />
</template>