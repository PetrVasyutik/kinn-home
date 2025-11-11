<template>
  <div class="top-banner">
    <div class="top-banner__image">
      <div class="top-banner__img">
        <picture>
          <source srcset="/images/img/banner.webp 1x, /images/img/banner@2x.webp 2x" type="image/webp">
          <img src="/images/img/banner.png" srcset="/images/img/banner.png 1x, /images/img/banner@2x.png 2x" width="1328" height="700" alt="Яблоки на тарелке и два стакана с янтарной жидкостью">
        </picture>
      </div>
    </div>
    <div class="top-banner__description">
      <div class="top-banner__subtitle">All collections</div>
      <h2 class="top-banner__title">Elevate Your Everyday</h2>
      <button class="btn btn--primary">Shop now</button>
    </div>
  </div>
</template>
<script setup></script>
<style scoped lang="scss">
.top-banner {
  width: 100%;
  padding: var(--layout-3);
  background-color: var(--color-bg-secondary);
  position: relative;
  box-sizing: border-box;

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
    bottom: 80px;
    right: 85px;
  }

  &__subtitle {
    font-size: 18px;
    color: var(--color-text-primary);
    text-transform: uppercase;
    letter-spacing: 1.8px;
    margin-bottom: var(--layout-2);
  }

  &__title {
    margin-bottom: var(--layout-6);
  }

  @media (max-width: 1024px) {
    &__description {
      bottom: 30px;
      right: 30px;
    }

    &__subtitle {
      font-size: 16px;
      margin-bottom: var(--layout-2);
    }

    &__title {
      margin-bottom: var(--layout-4);
    }
  }

  @media (max-width: 768px) {
    padding: 4px;

    &__description {
      bottom: 20px;
      right: 20px;
    }

    &__subtitle {
      font-size: 14px;
      letter-spacing: 1.4px;
      margin-bottom: var(--layout-1);
    }

    &__title {
      text-align: center;
      margin-bottom: var(--layout-3);
    }
  }

  @media (max-width: 480px) {
    &__description {
      bottom: 15px;
      right: 15px;
      left: 15px;
    }

    &__subtitle {
      font-size: 12px;
    }

    &__title {
      margin-bottom: var(--layout-1);
    }
  }
}
</style>
