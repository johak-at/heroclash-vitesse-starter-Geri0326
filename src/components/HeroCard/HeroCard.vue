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
      margin: auto;
      text-align: center;
      display: grid;
      grid-template-columns: 1fr 1fr;
      grid-template-rows: 1fr 1fr;
      width: 340px;
      height: 255px;
      border: 1px solid #F3F4F6;
      border-radius: 0.5rem;
    }
</style>
