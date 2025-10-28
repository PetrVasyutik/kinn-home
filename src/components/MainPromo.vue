<template>
  <div class="main-promo">
    <div class="main-promo__container">
      <div class="main-promo__image-container">
        <div class="main-promo__image">
        <div class="main-promo__img">
          <picture>
            <source srcset="/images/img/story.webp 1x, /images/img/story@2x.webp 2x" type="image/webp">
            <img src="/images/img/story.png" srcset="/images/img/story.png 1x, /images/img/story@2x.png 2x" width="743" height="618" alt="Our Design Story">
          </picture>
        </div>
      </div>
      </div>

      <div class="main-promo__description">
        <h2 class="main-promo__title">Our Design Story</h2>
        <p class="main-promo__text">
          We believe in thoughtful, intentional living. So we promise not to clutter your cabinets with one-off pieces you’ll rarely use. Our collection only includes items you’ll reach for every day. Because mindful living should be simple, not stressful.
        </p>
      </div>
    </div>
  </div>
</template>
<script setup></script>
<style scoped lang="scss">
.main-promo {
  width: 100%;
  padding: 16px;
  background-color: var(--color-bg-secondary);
  position: relative;
  box-sizing: border-box;

  &__container {
    display: flex;
    flex-direction: row;
    gap: 32px;
    justify-content: space-between;
  }
  &__image-container {
    max-width: 57%;
    flex-basis: 57%;
    flex-shrink: 0;
  }

  &__image {
    // aspect-ratio: 743 / 618;
    padding-top: calc(100% * 618 / 743);
    position: relative;

    box-sizing: border-box;
  }

  &__img {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;

    & img {
      width: 100%;
      height: 100%;
      object-fit: contain;
    }
  }
}
</style>
