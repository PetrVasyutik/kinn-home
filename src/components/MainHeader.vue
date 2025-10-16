<template>
  <header class="main-header">
    <div class="main-header__decor"></div>
    <div class="main-header__container">
      <div class="main-header__navigation">
        <ul class="main-header__navigation-list">
          <li
            class="main-header__navigation-item"
            v-for="item in navigation"
            :key="item.name">
            <a class="main-header__navigation-link" :href="item.href">
              {{ item.name }}
              <CheckMarkIcon v-if="item.component" />
            </a>
          </li>
        </ul>
      </div>
      <div class="main-header__logo">
        <LogoIcon />
      </div>
      <div class="main-header__actions">
        <BasketIcon />
        <SearchIcon />
        <UserIcon />
      </div>
    </div>
  </header>
</template>

<script setup>
import CheckMarkIcon from '@/components/icons/CheckMarkIcon.vue';
import LogoIcon from '@/components/icons/LogoIcon.vue';
import BasketIcon from '@/components/icons/BasketIcon.vue';
import SearchIcon from '@/components/icons/SearchIcon.vue';
import UserIcon from '@/components/icons/UserIcon.vue';

const navigation = [
  {
    name: 'Shop',
    href: '/',
    component: CheckMarkIcon,
  },
  {
    name: 'Style quiz',
    href: '/about',
  },
  {
    name: 'About us',
    href: '/contact',
  },
  {
    name: 'Stories',
    href: '/blog',
    component: CheckMarkIcon,
  },
];

</script>

<style scoped lang="scss">
.main-header {
  position: relative;
  max-width: 1424px;
  margin: 0 auto;

  &__decor {
    width: 100%;
    height: var(--layout-4);
    background-color: var(--color-bg-secondary);
  }

  &__container {
    width: 100%;
    padding: 0 var(--layout-12);
    display: flex;
    align-items: center;
    justify-content: space-between;
  }

  &__navigation-list {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: var(--layout-4);
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
}
</style>
