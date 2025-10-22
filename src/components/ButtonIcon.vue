<template>
  <div class="button-icon">
    <button
      class="button-icon__content"
      @click="$emit('click')"
    >
      <slot />
    </button>
  </div>
</template>
<script setup>
defineEmits(['click']);
</script>
<style scoped lang="scss">
.button-icon {

  &__content {
    outline: none;
    border: none;
    cursor: pointer;
    margin: 0;
    padding: 0;
    background-color: transparent;
    width: 100%;
    height: 100%;
    color: var(--color-text-primary);
    transition: all ease 0.3s;

    &:not(:disabled):hover,
    &:not(:disabled):focus {
      transform: scale(1.1);
    }

    &:disabled {
      opacity: 0.3;
    }
  }
}
</style>
