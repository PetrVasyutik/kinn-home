<template>
  <div class="main-carousel">
    <h2 class="main-carousel__title">#KinnMoments</h2>
    <div class="main-carousel__container">
      <ul class="main-carousel__list">
        <li class="main-carousel__item" v-for="image in images" :key="image.id">
          <div class="main-carousel__image">
            <div class="main-carousel__img">
              <picture>
                <source :srcset="image.webp" type="image/webp">
                <img :src="image.src" :srcset="image.srcset" width="320" height="320" :alt="image.alt">
              </picture>
            </div>
          </div>
        </li>
      </ul>
    </div>
  </div>
</template>
<script setup>
const { images } = defineProps({
  images: {
    type: Array,
    default: () => [],
  },
})
</script>
<style scoped lang="scss">
.main-carousel {
  padding: var(--layout-13) var(--layout-5);
  background-color: var(--color-bg-secondary);

  &__title {
    font-size: 25px;
    line-height: 32.4px;
    width: 100%;
    text-align: center;
    margin-bottom: var(--layout-6);
  }

  &__list {
    display: flex;
    gap: var(--layout-2);
    width: 100%;
  }

  &__item {
    width: calc((100% - var(--layout-2) * 3) / 4);
  }

  &__image {
    width: 100%;
    padding-top: calc(100% * 320 / 320);
    position: relative;
    background-color: var(--color-bg-img);
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

  @media (max-width: 1024px) {

    &__item {
    width: calc((100% - var(--layout-2)) / 2);
    }
  }
}
</style>
