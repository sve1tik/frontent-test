<script setup>
// Імпорт компонентів
import Footer from './components/Footer.vue'
import Header from './components/Header.vue'
import ProfileHeader from './components/ProfileHeader.vue'
import ProfileMain from './components/ProfileMain.vue'
import ProfileTeam from './components/ProfileTeam.vue'
import ProfileServices from './components/ProfileServices.vue'
import ProfileReviews from './components/ProfileReviews.vue'
</script>

<template>
  <Header />
  <main>
    <ProfileHeader />
    <ProfileMain />
    <ProfileTeam />
    <ProfileServices />
    <ProfileReviews />
  </main>
  <Footer />
</template>