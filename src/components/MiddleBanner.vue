<template>
  <div class="middle-banner">
    <div class="middle-banner__image">
      <div class="middle-banner__img">
        <picture>
          <source srcset="/images/img/essentials.webp 1x, /images/img/essentials@2x.webp 2x" type="image/webp">
          <img src="/images/img/essentials.png" srcset="/images/img/essentials.png 1x, /images/img/essentials@2x.png 2x" width="1328" height="700" alt="Яблоки на тарелке и два стакана с янтарной жидкостью">
        </picture>
      </div>
    </div>
    <div class="middle-banner__description">
      <div class="middle-banner__title">THE ESSENTIALS</div>
      <div class="middle-banner__subtitle">We believe minimalism means more. More space, more time, more meaningful moments.</div>
    </div>
  </div>
</template>
<script setup></script>
<style scoped lang="scss">
.middle-banner {
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
    justify-content: center;
    position: absolute;
    top: 60px;
    left: 0;
    width: 100%;
  }

  &__title {
    font-size: 17px;
    letter-spacing: 1.8px;
    text-transform: uppercase;
    width: 100%;
    text-align: center;
    margin-bottom: var(--layout-2);
  }

  &__subtitle {
    font-size: 50px;
    color: var(--color-text-primary);
    width: 100%;
    box-sizing: border-box;
    padding: 0 117px;
    text-align: center;
  }

  @media (max-width: 1024px) {
    &__description {
      top: 40px;
    }

    &__subtitle {
      font-size: 32px;
    }

    &__title {
      margin-bottom: var(--layout-1);
    }
  }

  @media (max-width: 768px) {

    &__subtitle {
      font-size: 24px;
      letter-spacing: 1.4px;
      padding: 0 40px;
    }
  }

  @media (max-width: 480px) {
    &__description {
      top: 25px;
    }

    &__subtitle {
      font-size: 14px;
    }

    &__title {
      font-size: 12px;
      margin-bottom: var(--layout-1);
    }
  }
}
</style>
