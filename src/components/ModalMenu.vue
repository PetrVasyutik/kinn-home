<template>
  <div class="modal-menu">
    <div class="modal-menu__navigation">
      <site-navigation />
    </div>
  </div>
</template>
<script setup>
import SiteNavigation from '@/components/SiteNavigation.vue';
</script>
<style scoped lang="scss">
.modal-menu {
  padding: var(--layout-8);
  background-color: var(--color-bg-primary);
  border-radius: 5px;
  box-shadow: 0 0 10px rgba(86, 89, 61, 0.7);
}
</style>
