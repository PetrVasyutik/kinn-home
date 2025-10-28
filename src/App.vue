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
        <section class="main__promo">
          <main-promo />
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
}
</style>
