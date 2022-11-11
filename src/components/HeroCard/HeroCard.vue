<script setup>
const props = defineProps(['hero'])
const showBiography = ref(false)
</script>

<template>
  <div grid class="card">
    <HeroImage :image-url="hero.images.md" @showBiography="showBiography = true" />

    <HeroStats :name="hero.name" :stats="hero.powerstats" :alignment="hero.biography.alignment" />
    <HeroModal
      v-if="showBiography" :name="hero.name" :alignment="hero.biography.alignment" :bio="hero.biography" :appearance="hero.appearance"
      :work="hero.work" :connections="hero.connections" @hideBiography="showBiography = false"
    />
  </div>
</template>

<style scoped>
    .card {

      border: 1px solid grey;
      grid-template-columns: 1fr 1fr;
      margin: auto;
      width: 330px;
        height: auto;
        margin-top: 20px;
        margin-bottom: 20px;
        border-radius: 0.5rem;

    }
</style>
