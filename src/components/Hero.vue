<script setup>
import BusInfo from './BusInfo.vue'
import busImg from '/img/bus.png'
import fireIcon from '/img/fire.svg'
import peoplesIcon from '/img/peoples.svg'
import trainIcon from '/img/train.svg'
import mapIcon from '/img/map.svg'
import cityIcon from '/img/city.svg'
import tel from '/img/tel.svg'
import world from '/img/world.svg'
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
                  <a href="https://stripe.com" target="_blank"><img :src="tel" alt="">https://stripe.com</a>
                  <a href="tel:+380735555555" target="_blank"><img :src="world" alt="">+38 (073) 555 55 55</a>
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

<style scoped>
.profile-header {
  background: #f8f8fd;
  padding-top: 40px;
  padding-bottom: 73px;
  background-image:
    url('/img/line-up-left.svg'), url('/img/line-down-left.svg'),
    url('/img/line-down-right.svg'), url('/img/line-center-right.svg'),
    url('/img/line-up-right.svg');
  background-repeat: no-repeat;
  background-position:
    left -4rem,
    left center,
    right 20rem,
    right center,
    right -7rem;
  background-size: contain, contain, 800px, contain, contain;
}
.profile__bread-crumbs {
  display: flex;
  gap: 10px;
  flex-wrap: wrap;
  list-style: none;
  padding: 0;
  margin: 0;
}
.profile__bread-crumbs a {
  color: #7c8493;
  font-size: 16px;
  font-weight: 400;
  transition: all 0.2s ease;
}
.profile__bread-crumbs a:hover {
  color: #25324b;
}
.profile__bread-crumbs li:last-child a {
  color: #25324b;
}
.profile__bread-crumbs li + li::before {
  content: '/';
  color: #7c8493;
  padding-right: 0.35rem;
}
.profile__info {
  padding-top: 40px;
}
.profile__info-wrapper {
  display: flex;
  align-items: center;
  gap: 100px;
}
.content__left img {
  width: 171px;
  height: 171px;
}

.content__description {
  padding-top: 24px;
}
.content__title {
  display: flex;
  gap: 30px;
  align-items: center;
  margin-bottom: 12px;
}
.content__title h2 {
  font-size: 48px;
  font-weight: 800;
  color: #25324b;
}
.content__title span {
  font-size: 16px;
  font-weight: 400;
  color: #4640de;
  border: 1px solid #4640de;
  padding: 4px 12px;
}
.content__callback {
  display: flex;
  gap: 20px;
}
.content__callback a {
  color: #4640de;
  font-size: 16px;
  font-weight: 600;
  display: inline-flex;
  gap: 8px;
  align-items: center;
  transition: all 0.2s ease;
}
.content__callback a:hover {
  opacity: 0.8;
}
@media (max-width: 992px) {
  .profile-header {
    padding-top: 30px;
    padding-bottom: 50px;
    background-size: contain, contain, 600px, contain, contain;
  }
  .profile__info-wrapper {
    flex-direction: column;
    gap: 30px;
    align-items: flex-start;
  }
  .content__left img {
    width: 140px;
    height: 140px;
  }
  .content__title {
    align-items: flex-start;
    gap: 15px;
  }
  .content__title h2 {
    font-size: 36px;
  }
}

@media (max-width: 768px) {
  .profile-header {
    padding-top: 20px;
    padding-bottom: 40px;
    background-size: contain, contain, 400px, contain, contain;
    background-position:
      left -2rem,
      left center,
      right 10rem,
      right center,
      right -4rem;
  }
  .profile__bread-crumbs {
    font-size: 14px;
  }
  .profile__info {
    padding-top: 30px;
  }
  .profile__info-wrapper {
    gap: 20px;
  }
  .content__left img {
    width: 120px;
    height: 120px;
  }
  .content__title h2 {
    font-size: 28px;
  }
  .content__title span {
    font-size: 14px;
    padding: 3px 10px;
  }
  .content__callback {
    gap: 15px;
  }
  .content__callback a {
    font-size: 14px;
  }
}

@media (max-width: 480px) {
  .profile-header {
    background-size: contain, contain, 300px, contain, contain;
  }
  .content__title h2 {
    font-size: 24px;
  }
  .content__title span {
    font-size: 12px;
    padding: 2px 8px;
  }
}
</style>