<script setup>
import { useCardsStore } from '~/store/cards'
const heroCards = ref([])
const hero = ref(null)

const cardsStore = useCardsStore()

onMounted(async () => {
  await cardsStore.loadCards()
  hero.value = cardsStore.heroCards[0].data
})
function switchHero(newNumber) {
  if (Number.isInteger(newNumber) && newNumber > 0 && newNumber < heroCards.value.length)
    hero.value = cardsStore.heroCards[newNumber - 1].data
}
</script>

<template>
  <a href="http://127.0.0.1:3333/">
    <img v-if="hero" src="heroclash-logo-lang.png" alt="heroclash logo" class="Logo"></a>
  <div class="Contents">
    <div>
      <H1 v-if="hero" class="Number">
        HERO NR.
      </H1>

      <HeroSelector @changeHero="switchHero" />

      <HeroCard v-if="hero" :hero="hero" class="card" />
    </div>
  </div>
</template>

<style>
.HeroFilter{
  border-width: 1px;
    border-style: solid;
    border-radius: 0.25rem;

}
div{
  display: block;
}
.Contents{
  display: flex;
  align-items: center;
  grid-gap: 0.25rem;
    gap: 0.25rem;
    flex-direction: column;
    justify-content: center;
    margin: 0 auto;
   width: 340px;
   height: 490px;
}
.Logo{

  cursor: pointer;
}
a{
  position: relative;
  left: 40%;
  display: flex;
  justify-content: center;
  max-width: 400px;
  margin-top: 1.25rem;
    margin-bottom: 1.25rem;
}
img{
  display: block;
    vertical-align: middle;
  max-width: 100%;
    height: auto;
    margin-top: 0px;
}
</style>

