<template>
  <div class="main-banner">
      <picture>
        <source srcset="/src/images/img/banner.webp 1x, /src/images/img/banner@2x.webp 2x" type="image/webp">
        <img src="/src/images/img/banner.png" srcset="/src/images/img/banner.png 1x, /src/images/img/banner@2x.png 2x" width="1328" height="700" alt="Яблоки на тарелке и два стакана с янтарной жидкостью">
      </picture>
    </div>
</template>
<script setup></script>
<style scoped lang="scss">
.main-banner {
  width: 100%;
  padding: 6px;
  background-color: var(--color-bg-secondary);

  & img {
    width: 1328px;
    height: 700px;
  }
}
</style>
