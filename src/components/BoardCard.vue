<template>
  <article class="board-card">
    <div class="board-card__image">
      <div class="board-card__img">
        <picture>
          <source srcset="@/images/img/board1.webp 1x, @/images/img/board1@2x.webp 2x" type="image/webp">
          <img src="@/images/img/board1.png" srcset="@/images/img/board1.png 1x, @/images/img/board1@2x.png 2x" width="410" height="410" alt="Разделочная доска">
        </picture>
      </div>
    </div>
    <h4 class="board-card__title">Maple Board - Short</h4>
    <div class="board-card__price">$98.00</div>
  </article>
</template>
<script setup></script>
<style scoped lang="scss">
.board-card {
  background-color: transparent;

  &__image {
    background-color: var(--color-bg-img);
    padding-top: calc(100% * 410 / 410);
    position: relative;
    max-width: 410px;
    margin-bottom: 15px;
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
    margin-bottom: 7px;
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
