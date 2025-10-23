<template>
  <div class="wrapper">
    <div class="container">
      <header class="header">
        <main-header />
      </header>
      <main class="main">
        <section class="main__banner">
          <main-banner />
        </section>
        <section class="main__slogan">
          <main-slogan />
        </section>
        <section class="main__board">
          <main-board />
        </section>
      </main>
      <footer class="footer"></footer>
    </div>
  </div>

</template>
<script setup>
import MainHeader from '@/components/MainHeader.vue';
import MainBanner from '@/components/MainBanner.vue';
import MainSlogan from '@/components/MainSlogan.vue';
import MainBoard from '@/components/MainBoard.vue';
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
}
</style>
