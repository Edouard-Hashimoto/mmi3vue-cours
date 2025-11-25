<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import MyHeader from './components/MyHeader.vue'
import DefaultLayout from './layouts/DefaultLayout.vue'
import MyButton from './components/MyButton.vue'
import MyTitle from './components/MyTitle.vue'
</script>

<template>
  <DefaultLayout>
    <template #header>
      <MyHeader />

      <nav>
        <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/about">About</RouterLink>
      </nav>

      <div>
        <h1 class="titreP">Welcome to My Website</h1>

        <!-- Boutons -->
        <MyButton>Default</MyButton>
        <MyButton variant="outline">Outline</MyButton>
        <MyButton class="-secondary">Secondary</MyButton>
        <MyButton class="-danger">Danger</MyButton>
        <MyButton class="-ghost">Ghost</MyButton>
        <MyButton size="small">Small</MyButton>
        <MyButton size="medium">Medium</MyButton>
        <MyButton size="large">Large</MyButton>
      </div>

      <div>
        <h1 class="titreP">Titre principal</h1>

        <MyTitle as="h2" size="subtitle">Titre Small</MyTitle>

        <MyTitle as="h1" size="texte2">Titre XL</MyTitle>

        <MyTitle as="h3" size="texte">Titre Medium</MyTitle>

        <MyTitle as="h2" class="-light">Titre Light</MyTitle>
      </div>
    </template>

    <RouterView />

    <template #aside><p>Aside</p></template>
    <template #footer><p>Footer</p></template>

    <p>paragraphe</p>
  </DefaultLayout>
</template>

<style scoped>
nav {
  display: flex;
  gap: 1rem;
}
</style>
