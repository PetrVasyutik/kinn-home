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
}
</style>
