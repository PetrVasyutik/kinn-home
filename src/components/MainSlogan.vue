<template>
  <div class="main-slogan">
    <p class="main-slogan__text">
      If your happy place is at the dinner table, we totally get that. That’s why we created products to help you find slow moments in a fast world.
    </p>
    <div class="main-slogan__buttons">
      <button class="main-slogan__btn">
        <span>Shop All <left-arrow-icon /></span>
      </button>
      <button class="main-slogan__btn">
        <span>Read Stories <left-arrow-icon /></span>
      </button>
    </div>
  </div>
</template>
<script setup>
import LeftArrowIcon from '@/components/icons/LeftArrowIcon.vue';
</script>
<style scoped lang="scss">
.main-slogan {
  width: 100%;
  padding: 10px 75px;
  box-sizing: border-box;

  &__text {
    font-size: 57px;
    text-align: center;
    margin-bottom: 15px;

    @media (max-width: 1024px) {
      font-size: 36px;
    }

    @media (max-width: 768px) {
      font-size: 28px;
    }
  }

  &__buttons {
    display: flex;
    flex-direction: row;
    gap: 70px;
    justify-content: center;
  }

  &__btn {
    background: none;
    border: none;
    color: var(--color-text-primary);
    font-family: var(--font-text-primary);
    font-size: var(--font-size-base);
    line-height: 25.6px;
    letter-spacing: 1.6px;
    border-bottom: 2px solid var(--color-text-primary);
    cursor: pointer;
    transition: transform ease 0.3s;

    &:hover {
      transform: scale(1.05);
    }
  }
}
</style>
