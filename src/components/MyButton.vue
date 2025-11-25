<script setup lang="ts">
defineProps<{
  href?: string
  variant?: 'default' | 'outline'
  size?: 'default' | 'small' | 'medium' | 'large'
}>()
</script>

<template>
  <a
    v-if="href"
    :href="href"
    class="button"
    :class="{
      '-outline': variant === 'outline',
      '-small': size === 'small',
      '-medium': size === 'medium',
      '-large': size === 'large',
    }"
  >
    <slot />
  </a>

  <button
    v-else
    class="button"
    :class="{
      '-outline': variant === 'outline',
      '-small': size === 'small',
      '-medium': size === 'medium',
      '-large': size === 'large',
    }"
  >
    <slot />
  </button>
</template>

<style lang="scss">
.button {
  --button-color: var(--color-text);
  --button-bg-color: var(--color-primary);
  --button-border-color: var(--color-primary);

  padding: rem(10) rem(20);
  background: var(--button-bg-color);
  color: var(--button-color);
  border: rem(1) solid var(--button-border-color);
  border-radius: rem(4);
  text-decoration: none;
  font-size: var(--font-size-base);
  

  @include medium-up {
    padding: rem(15) rem(25);
  }

  &:hover {
    --button-color: var(--color-primary);
    --button-bg-color: transparent;
  }

  &.-small {
    padding: rem(5) rem(10);
    font-size: var(--font-size-small);
    margin-left: 20px;
  }

  &.-medium {
    padding: rem(12) rem(22);
    font-size: var(--font-size-base);
    margin-left: 20px;
  }

  &.-large {
    padding: rem(30) rem(80);
    font-size: var(--font-size-large);
    margin-left: 20px;
  }

  &.-outline {
    --button-color: var(--color-primary);
    --button-bg-color: transparent;margin-left: 20px;

    &:hover {
      --button-color: var(--color-text);
      --button-bg-color: var(--color-primary);
    }
  }
}
</style>
