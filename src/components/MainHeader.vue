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
              <span> {{ item.name }} </span>
              <div class="main-header__navigation-icon">
                <CheckMarkIcon v-if="item.component" />
              </div>
            </a>
          </li>
        </ul>
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
  box-sizing: border-box;
  margin-bottom: var(--layout-5);

  &__decor {
    width: 100%;
    height: var(--layout-4);
    background-color: var(--color-bg-secondary);
  }

  &__container {
    max-width: 1424px;
    box-sizing: border-box;
    padding: var(--layout-6) calc(2 * var(--layout-8)) var(--layout-6) calc(2 * var(--layout-8));
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin: 0 auto;
    position: relative;
  }

  &__logo {
    position: absolute;
    left: 50%;
    transform: translateX(-50%);
  }

  &__navigation {
    max-width: 40%;
  }

  &__navigation-list {
    display: grid;
    grid-template-columns: repeat(4, auto);
    column-gap: var(--layout-8);
    row-gap: var(--layout-2);
  }

  &__navigation-link {
    color: var(--color-text-primary);
    text-transform: uppercase;
    display: flex;
    align-items: flex-start;
    gap: var(--layout-1);
    letter-spacing: 1.58px;
  }

  &__navigation-icon {
    width: 10px;
    height: 100%;
    display: flex;
    align-items: flex-start;
    justify-content: flex-start;
    padding-top: var(--layout-2);

    & svg {
      width: 10px;
      height: 8px;
    }
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
