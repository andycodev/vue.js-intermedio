<script setup lang="ts">
import NavBar from '@/shared/components/NavBar.vue';
import { pokemonRoute } from '../router';
import type { RouterLink } from '@/router/list-routes';


const routerLinks: RouterLink[] = pokemonRoute.children?.map((link) => {
  return {
    name: '',
    path: '',
    title: ''
  }
}) || [];

</script>

<template>
  <NavBar :links="routerLinks" is-secondary />
  <div>
    <h4>Pokemon Layout</h4>
    <RouterView />
  </div>
</template>
