<script setup>
const heroCards = ref([])
const counter = ref(1)
const hero = ref('')

onMounted(async () => {
  let response = await fetch('https://hcpb.seiwald.club/api/collections/heroes/records?perPage=999&page=1')

  let data = await response.json()

  heroCards.value.push(...data.items)

  response = await fetch('https://hcpb.seiwald.club/api/collections/heroes/records?perPage=999&page=2')

  data = await response.json()

  heroCards.value.push(...data.items)

  addValue()
})
function addValue() {
  hero.value = heroCards.value[counter.value - 1].data
}

function isPositive() {
  if (counter.value !== 1)
    counter.value--
}
</script>

<template>
  <a href="http://127.0.0.1:3333/">
    <img v-if="hero" src="heroclash-logo-lang.png" alt="heroclash logo" class="Logo"></a>

  <H1 v-if="hero" class="Number">
    HERO NR.
  </H1>
  <div class="counter">
    <span class="Arrows" @click="isPositive(), addValue()">&lt;  </span>
    <input v-model="counter" type="number">
    <span class="Arrows" @click="counter++, addValue()">></span>
  </div>

  <HeroCard v-if="hero" :hero="hero" class="card" />
</template>

<style>
*{
  box-sizing: border-box;
    border-width: 0;
    border-style: solid;
    border-color: #e5e7eb;
}
a{
  display: flex;
  justify-content: center;
  max-width: 400px;
}
img{
  display: block;
    vertical-align: middle;
  max-width: 100%;
    height: auto;
    margin-top: 0px;
    cursor: pointer;
}
.Logo{

}
.Number{
  display: flex;
  align-items: flex-start;
  justify-content: center;
  font-family: "action-comics-black";
  font-size: 1.75rem;
  margin: 0;
  filter: drop-shadow(2px 2px 2px);
    -webkit-text-stroke: 1px #000;
    background: linear-gradient(45deg, #f7a823, #e4003a);
    -webkit-text-fill-color: transparent;
    -webkit-background-clip: text;
    text-transform: uppercase;
    transition: all 0.1s ease-in-out;
}
.counter{
  display: flex;
  align-items: center;
  justify-content: center;
}
input[type="number"] {
  text-align: center;
  border: none;
  width: 170px;
  height: 60px;
}
input{
  font-size: 1.75rem;
  font-family: "action-comics-black";
  filter: drop-shadow(2px 2px 2px);
    -webkit-text-stroke: 1px #000;
    background: linear-gradient(45deg, #f7a823, #e4003a);
    -webkit-text-fill-color: transparent;
    -webkit-background-clip: text;
    text-transform: uppercase;
    transition: all 0.1s ease-in-out;
    text-align: center;
}
.Arrows
  {
    font-family: "ComicKings";
    font-size: 3.75rem;
    filter: drop-shadow(2px 2px 2px);
    -webkit-text-stroke: 1px #000;
    background: linear-gradient(45deg, #f7a823, #e4003a);
    -webkit-text-fill-color: transparent;
    -webkit-background-clip: text;
    text-transform: uppercase;
    transition: all 0.1s ease-in-out;
    cursor: pointer;
}
</style>

