<script setup lang="ts">
import type { RouterLink } from '@/router/list-routes';
//import { routerLinks, type RouterLink } from '@/router/list-routes';

interface Props {
  title?: string;
  links: RouterLink[];
}

//defineProps<Props>()
/* const props = withDefaults(defineProps<Props>(), {
  title: 'CompositionApp'
})
console.log('props', props); */

withDefaults(defineProps<Props>(), {
  title: 'CompositionApp',
  // links: () => [] //opcional
})


</script>

<template>
  <nav>
    <img alt="Vue logo" class="logo" src="@/assets/logo.svg" width="25" height="25" />
    <!-- <span v-if="$props.title">{{ $props.title }}</span> -->
    <!-- <span>{{ $props.title || 'CompositionApp' }}</span> -->
    <span>{{ $props.title }}</span>

    <RouterLink v-for="link in $props.links" :key="link.path" :to="link.path">{{ link.title }}</RouterLink>

    <!--  <RouterLink to="/about">About</RouterLink>
    <RouterLink to="/counter">Counter</RouterLink> -->
  </nav>
</template>

<style scoped>
nav {
  align-items: flex-start;
  display: flex;
  font-size: 12px;
  margin-top: 10px;
  text-align: center;
  width: 100%;
}

img {
  margin-right: 5px;
}

span {
  margin-right: 10px;
}

a {
  margin-right: 5px;
}

nav {
  width: 100%;
  font-size: 12px;
  text-align: center;
  margin-top: 2rem;
}

nav a.router-link-exact-active {
  color: var(--color-text);
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
}

nav a:first-of-type {
  border: 0;
}
</style>
