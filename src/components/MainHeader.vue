<template>
  <header class="main-header">
    <div class="main-header__decor"></div>
    <div class="main-header__container">
      <button class="main-header__btn" :class="{ 'main-header__btn--open': isMenuOpen }" @click="OpenMenu"></button>
      <div class="main-header__navigation">
        <site-navigation />
      </div>
      <div class="main-header__logo">
        <LogoIcon />
      </div>
      <div class="main-header__actions">
        <UserIcon />
        <SearchIcon />
        <BasketIcon />
      </div>
    </div>
    <transition name="menu" appear>
      <div v-if="isMenuOpen" class="main-header__menu-modal">
        <modal-menu />
      </div>
    </transition>
  </header>
</template>

<script setup>
import LogoIcon from '@/components/icons/LogoIcon.vue';
import BasketIcon from '@/components/icons/BasketIcon.vue';
import SearchIcon from '@/components/icons/SearchIcon.vue';
import UserIcon from '@/components/icons/UserIcon.vue';
import SiteNavigation from '@/components/SiteNavigation.vue';
import ModalMenu from '@/components/ModalMenu.vue';
import { ref, onMounted, onUnmounted } from 'vue';

const isMenuOpen = ref(false);

const OpenMenu = () => {
  isMenuOpen.value = !isMenuOpen.value;
}

const closeMenu = () => {
  isMenuOpen.value = false;
  // Сбрасываем фокус с кнопки, чтобы убрать стили по умолчанию
  const button = document.querySelector('.main-header__btn');
  if (button) {
    button.blur();
  }
}

// Закрытие по ESC
const handleKeydown = (event) => {
  if (event.key === 'Escape' && isMenuOpen.value) {
    closeMenu();
  }
}

// Закрытие по клику вне модалки
const handleClickOutside = (event) => {
  const modal = event.target.closest('.main-header__menu-modal');
  const button = event.target.closest('.main-header__btn');

  if (!modal && !button && isMenuOpen.value) {
    closeMenu();
  }
}

onMounted(() => {
  document.addEventListener('keydown', handleKeydown);
  document.addEventListener('click', handleClickOutside);
});

onUnmounted(() => {
  document.removeEventListener('keydown', handleKeydown);
  document.removeEventListener('click', handleClickOutside);
});

</script>

<style scoped lang="scss">
.main-header {
  position: relative;
  box-sizing: border-box;
  margin-bottom: var(--layout-5);
  width: 100%;

  &__decor {
    width: 100%;
    height: var(--layout-4);
    background-color: var(--color-bg-secondary);
  }

  &__container {
    max-width: 1424px;
    box-sizing: border-box;
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin: 0 auto;
    padding: 30px 30px 20px 30px;

    position: relative;
  }

  &__logo {
    position: absolute;
    left: 50%;
    transform: translateX(-50%);
  }

  &__navigation {
    max-width: 40%;
    transition: all ease 0.3s;
  }

  &__actions {
    display: flex;
    align-items: center;
    gap: var(--layout-4);

    & svg {
      width: 32px;
      height: 32px;
    }
  }

  &__btn {
    display: none;
    transition: all ease 0.3s;
    position: absolute;
    left: 12px;
    background: none;
    border: none;
    cursor: pointer;
    padding: 8px;
    width: 40px;
    height: 40px;
    outline: none;

    &:focus {
      outline: none;
      box-shadow: none;
    }

    &:active {
      transform: none;
    }

    &::before,
    &::after {
      content: '';
      position: absolute;
      width: 24px;
      height: 2px;
      background-color: var(--color-text-primary);
      transition: all ease 0.3s;
      left: 50%;
      transform: translateX(-50%);
    }

    &::before {
      top: 12px;
    }

    &::after {
      bottom: 12px;
    }

    &::before {
      box-shadow: 0 7px 0 var(--color-text-primary);
    }
  }

  &__menu-modal {
    position: absolute;
    top: 70px;
    left: 70px;
    z-index: 100;
    display: none;
  }

  .menu-enter-active,
  .menu-leave-active {
    transition: all 0.3s ease;
  }

  .menu-enter-from {
    opacity: 0;
    transform: translateY(-20px) scale(0.95);
  }

  .menu-leave-to {
    opacity: 0;
    transform: translateY(-20px) scale(0.95);
  }

  .menu-enter-to,
  .menu-leave-from {
    opacity: 1;
    transform: translateY(0) scale(1);
  }

  &__btn--open {
    &::before {
      transform: translateX(-50%) translateY(8px) rotate(45deg);
      box-shadow: none;
    }

    &::after {
      transform: translateX(-50%) translateY(-8px) rotate(-45deg);
    }
  }

  @media (max-width: 1024px) {

    margin-bottom: var(--layout-3);

    &__decor {
      height: var(--layout-3);
      background-color: var(--color-bg-secondary);
    }

    &__container {
      justify-content: end;
      padding: 15px 15px 10px 15px;
    }

    &__navigation {
      display: none;
    }

    &__actions svg {
      width: 24px;
      height: 24px;
    }

    &__btn {
      display: block;
    }

    &__menu-modal {
      display: block;
    }
  }

  @media (max-width: 767px) {
    margin-bottom: var(--layout-2);

    &__container {
      padding: 10px;
    }

    &__actions {
      gap: var(--layout-3);
    }
  }

  @media (max-width: 480px) {

    &__logo svg {
      width: 70px;
    }

    &__actions {
      gap: var(--layout-2);
    }

    &__actions svg {
      width: 18px;
      height: 18px;
    }
  }
}
</style>
