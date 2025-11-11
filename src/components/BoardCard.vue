<template>
  <article class="board-card" v-if="board">
    <div class="board-card__image">
      <div class="board-card__img">
        <picture>
          <source :srcset="board.webp" type="image/webp">
          <img :src="board.src" :srcset="board.srcset" width="410" height="410" alt="Разделочная доска">
        </picture>
      </div>
    </div>
    <h4 class="board-card__title">{{ board.title }}</h4>
    <div class="board-card__price">{{ board.price }}</div>
  </article>
</template>
<script setup>
const { board } = defineProps({
  board: {
    type: Object,
    required: true,
  },
});
</script>
<style scoped lang="scss">
.board-card {
  background-color: transparent;

  &__image {
    background-color: var(--color-bg-img);
    padding-top: calc(100% * 410 / 410);
    position: relative;
    max-width: 410px;
    margin-bottom: var(--layout-3);
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

  &__title {
    width: 100%;
    text-align: center;
    margin-bottom: var(--layout-2);
    font-size: var(--font-size-base);
    line-height: 32.4px;
    letter-spacing: 0;
  }

  &__price {
    width: 100%;
    text-align: center;
  }
}
</style>
