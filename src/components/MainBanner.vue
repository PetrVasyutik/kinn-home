<template>
  <div class="main-banner">
    <div class="main-banner__image">
      <div class="main-banner__img">
        <picture>
          <source srcset="/src/images/img/banner.webp 1x, /src/images/img/banner@2x.webp 2x" type="image/webp">
          <img src="/src/images/img/banner.png" srcset="/src/images/img/banner.png 1x, /src/images/img/banner@2x.png 2x" width="1328" height="700" alt="Яблоки на тарелке и два стакана с янтарной жидкостью">
        </picture>
      </div>
    </div>
    <div class="main-banner__description">
      <div class="main-banner__subtitle">All collections</div>
      <h2 class="main-banner__title">Elevate Your Everyday</h2>
      <button class="btn btn--primary">Shop now</button>
    </div>
  </div>
</template>
<script setup></script>
<style scoped lang="scss">
.main-banner {
  width: 100%;
  padding: 6px;
  background-color: var(--color-bg-secondary);
  position: relative;

  &__image {
    padding-top: calc(100% * 700 / 1328);
    position: relative;
    max-width: 1328px;
    margin: 0 auto;
  }

  &__img {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;

    & img {
      width: 100%;
      height: 100%;
      object-fit: cover;
    }
  }

  &__description {
    display: flex;
    flex-direction: column;
    align-items: end;
    position: absolute;
    bottom: 77px;
    right: 85px;
  }

  &__subtitle {
    font-size: 18px;
    color: var(--color-text-primary);
    text-transform: uppercase;
    letter-spacing: 1.8px;
    margin-bottom: 10px;
  }

  &__title {
    font-size: 45px;
    margin-bottom: var(--layout-6);
  }
}
</style>
