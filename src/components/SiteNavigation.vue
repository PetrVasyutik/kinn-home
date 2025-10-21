<template>
  <div class="site-navigation">
    <ul class="site-navigation__list">
      <li
        class="site-navigation__item"
        v-for="item in navigation"
        :key="item.name">
        <a class="site-navigation__link" :href="item.href">
          <span> {{ item.name }} </span>
          <div class="site-navigation__icon">
            <CheckMarkIcon v-if="item.component" />
          </div>
        </a>
      </li>
    </ul>
  </div>
</template>
<script setup>
import CheckMarkIcon from '@/components/icons/CheckMarkIcon.vue';

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
.site-navigation {

  &__list {
    display: grid;
    grid-template-columns: repeat(4, auto);
    column-gap: var(--layout-8);
    row-gap: var(--layout-2);
  }

  &__link {
    color: var(--color-text-primary);
    text-transform: uppercase;
    display: flex;
    align-items: flex-start;
    gap: var(--layout-1);
    letter-spacing: 1.58px;
    transition: transform ease 0.3s;

    &:hover {
      transform: scale(1.05);
    }
  }

  &__icon {
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

  @media (max-width: 1324px) {

    &__list {
      column-gap: var(--layout-3);
      font-size: 14px;
      letter-spacing: 1.4px;
    }

    &__icon {
      & svg {
        width: 8px;
        height: 6px;
      }
    }
  }
}

@media (max-width: 1024px) {

  .site-navigation {
    &__list {
      display: flex;
      flex-direction: column;
      align-items: center;
      font-size: var(--font-base);
      row-gap: var(--layout-4);
    }

  }
}
</style>
