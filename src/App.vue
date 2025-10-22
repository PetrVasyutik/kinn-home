<template>
  <div class="wrapper">
    <div class="container">
      <header class="header">
        <main-header />
      </header>
      <main class="main">
          <main-banner />
      </main>
      <footer class="footer"></footer>
    </div>
  </div>

</template>
<script setup>
import MainHeader from '@/components/MainHeader.vue';
import MainBanner from '@/components/MainBanner.vue';
</script>
<style scoped lang="scss">
.wrapper {
  width: 100%;
}
</style>
