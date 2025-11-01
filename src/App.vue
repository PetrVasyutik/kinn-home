<template>
  <div class="wrapper">
    <div class="container">
      <header class="header">
        <main-header />
      </header>
      <main class="main">
        <section class="main__banner">
          <top-banner />
        </section>
        <section class="main__slogan">
          <main-slogan />
        </section>
        <section class="main__board">
          <main-board />
        </section>
        <section class="main__middle-banner">
          <middle-banner />
        </section>
        <section
          class="main__promo"
          v-for="promo in promos"
          :key="promo.id"
        >
          <main-promo :promo="promo" />
        </section>
        <section class="main__signup">
          <main-signup />
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
</script>
<style scoped lang="scss">
.main {

  &__banner {
    margin-bottom: var(--layout-section-large);
  }

  &__slogan {
    margin-bottom: var(--layout-section-large);
  }

  &__board {
    margin-bottom: var(--layout-section-small);
  }

  &__middle-banner {
    margin-bottom: var(--layout-section-small);
  }

  &__promo {
    margin-bottom: var(--layout-section-small);
  }

  &__signup {
    margin-bottom: var(--layout-section-small);
  }
}
</style>
