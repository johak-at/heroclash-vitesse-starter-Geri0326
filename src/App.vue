<script setup lang="ts">
// https://github.com/vueuse/head
// you can use this to manipulate the document head in any components,
// they will be rendered correctly in the html results with vite-ssg
useHead({
  title: 'HeroClash',
  meta: [
    { name: 'description', content: 'A Card Game developed' },
    {
      name: 'theme-color',
      content: computed(() => isDark.value ? '#00aba9' : '#ffffff'),
    },
  ],
  link: [
    {
      rel: 'icon',
      type: 'image/svg+xml',
      href: '/heroclash-favicon.svg',
    },
  ],
})
</script>

<template>
  <RouterView />
</template>

<style>
@font-face {
  font-family: "action-comics-black";
  src: local("action-comics-black"),   url(./fonts/ActionComics/action-comics-black.ttf) format("truetype");
}
@font-face {
  font-family: "ComicKings";
  src: local("ComicKings"),   url(./fonts/ComicKings/ComicKings.ttf) format("truetype");
}
</style>
