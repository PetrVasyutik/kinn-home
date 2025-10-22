<template>
  <div class="button-actions">
    <ul class="button-actions__list">
      <li
        class="button-actions__item"
        v-for="button in buttons"
        :key="button"
      >
        <button-icon @click="button.action">
          <component :is="button.component" />
        </button-icon>
      </li>
    </ul>
  </div>
</template>
<script setup>
import UserIcon from '@/components/icons/UserIcon.vue';
import SearchIcon from '@/components/icons/SearchIcon.vue';
import BasketIcon from '@/components/icons/BasketIcon.vue';
import ButtonIcon from '@/components/ButtonIcon.vue';

// Определяем функции для обработки кликов
const LoginOpen = () => {
  console.log('Login clicked');
  // Здесь можно добавить логику открытия модального окна входа
};

const SearchOpen = () => {
  console.log('Search clicked');
  // Здесь можно добавить логику открытия поиска
};

const BasketOpen = () => {
  console.log('Basket clicked');
  // Здесь можно добавить логику открытия корзины
};

const buttons = [
  {
    component: UserIcon,
    action: LoginOpen,
  },
  {
    component: SearchIcon,
    action: SearchOpen,
  },
  {
    component: BasketIcon,
    action: BasketOpen,
  },
]
</script>
<style scoped lang="scss">
.button-actions {

  &__list {
    display: flex;
    flex-direction: row;
    gap: var(--layout-4);
  }

  &__item {
    width: 32px;
    height: 32px;
  }

  @media (max-width: 1024px) {
    &__list {
      gap: var(--layout-3);
    }

    &__item {
      width: 24px;
      height: 24px;
    }
  }

  @media (max-width: 480px) {

    &__list {
      gap: var(--layout-2);
    }

    &__item {
      width: 18px;
      height: 18px;
    }
  }
}
</style>
