<template>
  <div class="main-promo" :class="`main-promo--${promo.align}`">
    <div class="main-promo__container">
      <div class="main-promo__image-container">
        <div class="main-promo__image">
        <div class="main-promo__img">
          <picture>
            <source :srcset="promo.imageWebp + ' 1x, ' + promo.imageWebp2x + ' 2x'" type="image/webp">
            <img :src="promo.image" :srcset="promo.image2x" width="743" height="618" alt="Our Design Story">
          </picture>
        </div>
      </div>
      </div>

      <div class="main-promo__description">
        <h2 class="main-promo__title">{{ promo.title }}</h2>
        <div class="main-promo__text">{{ promo.text }}</div>
      </div>
    </div>
  </div>
</template>
<script setup>
const { promo } = defineProps({
  promo: {
    type: Object,
    required: true,
  },
});
</script>
<style scoped lang="scss">
.main-promo {
  width: 100%;
  padding: 16px;
  background-color: var(--color-bg-secondary);
  position: relative;
  box-sizing: border-box;

  &--right {
    .main-promo__image-container {
      order: 2;
    }

    .main-promo__description {
      order: 1;
    }
  }

  &__container {
    display: flex;
    flex-direction: row;
    gap: 32px;
    justify-content: space-between;
  }
  &__image-container {
    max-width: 57%;
    flex-basis: 57%;
    flex-shrink: 0;
  }

  &__image {
    // aspect-ratio: 743 / 618;
    padding-top: calc(100% * 618 / 743);
    position: relative;

    box-sizing: border-box;
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
      padding: 63px 87px;
  }

  &__title {
    font-size: 29px;
    line-height: 38.9px;
    margin-bottom: calc(var(--layout-6) * 2);
    width: 100%;
    text-align: center;
    position: relative;

    &::after {
      content: '';
      display: block;
      width: 40px;
      height: 1px;
      background-color: var(--color-text-primary);
      left: 50%;
      bottom: calc(-1 * var(--layout-6));
      transform: translateX(-50%);
      position: absolute;
    }
  }

  &__text {
    font-size: 20px;
    line-height: 32.4px;
    width: 100%;
    text-align: center;
  }

  @media (max-width: 1200px) {
    &__description {
      padding: 40px 60px;
    }
  }

  @media (max-width: 1024px) {

    &__description {
      padding: 20px 30px;
    }

    &__title {
      font-size: 24px;
      line-height: 32.4px;
      margin-bottom: var(--layout-6);

      &::after {
        bottom: calc(-1 * var(--layout-4));
      }
    }

    &__text {
      font-size: 18px;
      line-height: 28.8px;
    }
  }

  @media (max-width: 768px) {

    &--right {
      .main-promo__image-container {
      order: 1;
      }
    }

    &__container {
      flex-direction: column;
    }

    &__image-container {
      max-width: 100%;
      flex-basis: 100%;
    }

    &__title {
      font-size: 20px;
      line-height: 28.8px;
    }

    &__text {
      font-size: 16px;
      line-height: 25.6px;
    }
  }
}
</style>
