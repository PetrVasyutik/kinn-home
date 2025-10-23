<template>
  <div class="main-board">
    <h3 class="main-board__title">Maple Board Collections</h3>
    <div class="main-board__list">
      <div class="main-board__item">
        <board-card />
      </div>
    </div>
  </div>
</template>
<script setup>
import BoardCard from '@/components/BoardCard.vue';
</script>
<style scoped lang="scss">
.main-board {
  padding: 65px 32px;
  background-color: var(--color-bg-secondary);

  &__title {
    width: 100%;
    text-align: center;
    margin-bottom: var(--layout-section-large);
    font-size: 24px;
    line-height: 32.4px;
    letter-spacing: 0;
    font-weight: 400;
  }

  &__list {
    display: flex;
    flex-direction: row;
    gap: 32px;
  }

  &__item {
    width: calc(100% / 3);
  }
}
</style>
