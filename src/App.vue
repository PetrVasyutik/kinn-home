<template>
  <div class="wrapper">
    <div class="container">
      <header class="header">
        <main-header />
      </header>
      <main class="main">
        <section class="main-section main-section--large">
          <top-banner />
        </section>
        <section class="main-section main-section--large">
          <main-slogan />
        </section>
        <section class="main-section">
          <main-board />
        </section>
        <section class="main-section">
          <middle-banner />
        </section>
        <section
          class="main-section"
          v-for="promo in promos"
          :key="promo.id"
        >
          <main-promo :promo="promo" />
        </section>
        <section class="main-section">
          <main-signup />
        </section>
        <section class="main-section main-section--large">
          <main-carousel :images="images"/>
        </section>
      </main>
      <footer class="footer"></footer>
    </div>
  </div>

</template>
<script setup>
import MainHeader from '@/components/MainHeader.vue';
import TopBanner from '@/components/TopBanner.vue';
import MainSlogan from '@/components/MainSlogan.vue';
import MainBoard from '@/components/MainBoard.vue';
import MiddleBanner from '@/components/MiddleBanner.vue'
import MainPromo from '@/components/MainPromo.vue'
import MainSignup from '@/components/MainSignup.vue'
import MainCarousel from '@/components/MainCarousel.vue'

const promos = [
  {
    id: 1,
    title: 'Our Design Story',
    text: 'We believe in thoughtful, intentional living. So we promise not to clutter your cabinets with one-off pieces you’ll rarely use. Our collection only includes items you’ll reach for every day. Because mindful living should be simple, not stressful.',
    image: '/images/img/story.png',
    image2x: '/images/img/story@2x.png',
    imageWebp: '/images/img/story.webp',
    imageWebp2x: '/images/img/story@2x.webp',
    align: 'left',
  },
  {
    id: 2,
    title: 'Your Table Your Time',
    text: 'Our modern lives keep us in constant motion. But what keeps us moving isn’t always what moves us. Our time at the table is our pause button. Meals can become moments and moments can become memories. So grab a plate, pull up a seat, and stay a while',
    image: '/images/img/table.png',
    image2x: '/images/img/table@2x.png',
    imageWebp: '/images/img/table.webp',
    imageWebp2x: '/images/img/table@2x.webp',
    align: 'right',
  },
];

const images = [
  {
    id: 1,
    src: '/images/img/story.png',
    srcset: '/images/img/story.png 1x, /images/img/story@2x.png 2x',
    webp: '/images/img/story.webp 1x, /images/img/story@2x.webp 2x',
    alt: '',
  },
  {
    id: 2,
    src: '/images/img/moment2.png',
    srcset: '/images/img/moment2.png 1x, /images/img/moment2@2x.png 2x',
    webp: '/images/img/moment2.webp 1x, /images/img/moment2@2x.webp 2x',
    alt: '',
  },
  {
    id: 3,
    src: '/images/img/moment3.png',
    srcset: '/images/img/moment3.png 1x, /images/img/moment3@2x.png 2x',
    webp: '/images/img/moment3.webp 1x, /images/img/moment3@2x.webp 2x',
    alt: '',
  },
  {
    id: 4,
    src: '/images/img/table.png',
    srcset: '/images/img/table.png 1x, /images/img/table@2x.png 2x',
    webp: '/images/img/table.webp 1x, /images/img/table@2x.webp 2x',
    alt: '',
  },
];

</script>
<style scoped lang="scss">
</style>
