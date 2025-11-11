<template>
  <div class="main-board">
    <h3 class="main-board__title">Maple Board Collections</h3>
    <div class="main-board__list">
      <div class="main-board__item"
        v-for="board in boards"
        :key="board.id"
      >
        <board-card :board="board" />
      </div>
    </div>
  </div>
</template>
<script setup>
import BoardCard from '@/components/BoardCard.vue';

const boards = [
  {
    id: 1,
    title: 'Maple Board - Short',
    price: '$98.00',
    src: '/images/img/board1.png',
    srcset: '/images/img/board1.png 1x, /images/img/board1@2x.png 2x',
    webp: '/images/img/board1.webp 1x, /images/img/board1@2x.webp 2x',
  },
  {
    id: 2,
    title: 'Maple Board - long',
    price: '$125.00',
    src: '/images/img/board2.png',
    srcset: '/images/img/board2.png 1x, /images/img/board2@2x.png 2x',
    webp: '/images/img/board2.webp 1x, /images/img/board2@2x.webp 2x',
  },
  {
    id: 1,
    title: 'Maple Board - Short',
    price: '$98.00',
    src: '/images/img/board1.png',
    srcset: '/images/img/board1.png 1x, /images/img/board1@2x.png 2x',
    webp: '/images/img/board1.webp 1x, /images/img/board1@2x.webp 2x',
  },
];
</script>
<style scoped lang="scss">
.main-board {
  padding: var(--layout-12) var(--layout-8);
  background-color: var(--color-bg-secondary);

  &__title {
    width: 100%;
    text-align: center;
    margin-bottom: var(--layout-section-large);
    line-height: 32.4px;
    letter-spacing: 0;
    font-weight: 400;
  }

  &__list {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 32px;

    @media (max-width: 1024px) {
      grid-template-columns: repeat(2, 1fr);
    }

    @media (max-width: 480px) {
      grid-template-columns: repeat(1, 1fr);
    }
  }
}
</style>
