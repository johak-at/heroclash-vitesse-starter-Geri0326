<script setup>
const heroCards = ref([])
const hero = ref('')

onMounted(async () => {
  let response = await fetch('https://hcpb.seiwald.club/api/collections/heroes/records?perPage=999&page=1')

  let data = await response.json()

  heroCards.value.push(...data.items)

  response = await fetch('https://hcpb.seiwald.club/api/collections/heroes/records?perPage=999&page=2')

  data = await response.json()

  heroCards.value.push(...data.items)

  hero.value = heroCards.value[15].data
})
</script>

<template>
  <img v-if="hero" src="heroclash-logo-lang.png" alt="heroclash logo" class="Logo">

  <H1 v-if="hero" class="Number">
    HERO NR.
  </H1>
  <HeroCard v-if="hero" :hero="hero" />
</template>

<style>
.Logo{
  position: absolute;
  top: 15px;
  width: 321px;
  left: 39.58%;
  max-width: 100%;
    height: auto;
    margin-top: 0px;
  }
.Number{
  position: absolute;
  top: 15.5%;
  left: 44%;
  font-family: "action-comics-black";
  font-size: 1.35rem;
  filter: drop-shadow(2px 2px 2px);
    -webkit-text-stroke: 1px #000;
    background: linear-gradient(45deg, #f7a823, #e4003a);
    -webkit-text-fill-color: transparent;
    -webkit-background-clip: text;
    text-transform: uppercase;
    transition: all 0.1s ease-in-out;
}
</style>

