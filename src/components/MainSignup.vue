<template>
  <div class="main-signup">
    <div class="main-signup__container">
      <h2 class="main-signup__title">Sign up for our newsletter</h2>
      <div class="main-signup__text">Receive special offers and first look at new products.</div>
      <form class="main-signup__form" @submit.prevent="handleSubmit">
        <div class="main-signup__input-wrapper">
          <input
            v-model="email"
            type="email"
            placeholder="Enter your email"
            class="main-signup__input"
            :class="{ 'main-signup__input--error': error }"
            @blur="validateEmail"
            @input="clearError"
          >
        </div>
        <button type="submit" class="btn btn--primary">Subscribe</button>
      </form>
      <div v-if="error" class="main-signup__error">{{ error }}</div>
    </div>
  </div>
</template>
<script setup>
import { ref } from 'vue';

const email = ref('');
const error = ref('');

const validateEmail = () => {
  if (!email.value) {
    error.value = 'Email is required';
    return false;
  }

  const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
  if (!emailRegex.test(email.value)) {
    error.value = 'Please enter a valid email address';
    return false;
  }

  error.value = '';
  return true;
};

const clearError = () => {
  if (error.value) {
    error.value = '';
  }
};

const handleSubmit = () => {
  if (validateEmail()) {
    // Здесь можно добавить логику отправки
    console.log('Email submitted:', email.value);
    email.value = '';
    error.value = '';
  }
};
</script>
<style scoped lang="scss">
.main-signup {
  width: 100%;
  background-color: var(--color-bg-secondary);
  padding: var(--layout-6);
  position: relative;
  box-sizing: border-box;

  &__container {
    text-align: center;
    padding: var(--layout-6);
  }

  &__title {
    font-size: 29px;
    line-height: 38.9px;
    margin-bottom: var(--layout-3);
  }

  &__text {
    font-size: 17px;
    line-height: 28.8px;
    margin-bottom: var(--layout-12);
  }

  &__form {
    display: flex;
    flex-direction: row;
    gap: var(--layout-3);
    justify-content: center;
    align-items: flex-end;
  }

  &__input-wrapper {
    display: flex;
    flex-direction: column;
  }

  &__input {
    width: 340px;
    height: 40px;
    border: none;
    border-bottom: 1px solid var(--color-text-primary);
    background: transparent;
    text-align: center;
    transition: border-color 0.3s ease;

    &::placeholder {
      opacity: 0.3;
    }

    &:focus {
      outline: none;
    }

    &--error {
      border-bottom-color: #d32f2f;
    }
  }

  &__error {
    margin-top: 12px;
    font-size: 14px;
    color: #d32f2f;
    text-align: center;
    min-height: 20px;
  }

  & .btn {
    padding: var(--layout-2) var(--layout-3);
  }
}
</style>
