<script setup lang="ts">
defineProps<{
  as: 'h1' | 'h2' | 'h3'
  size?: 'subtitle' | 'texte' | 'texte2' 
}>()
</script>

<template>
  <component
    :is="as"
    class="title"
    :class="[
      size ? `-${size}` : '',
      $attrs.class   /* permet de passer titreP ou autres classes supplémentaires */
    ]"
  >
    <slot />
  </component>
</template>
