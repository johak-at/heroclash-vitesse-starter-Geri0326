<script setup>
const heroCards = ref([])
const hero = ref('')

let counter = ref(1);

onMounted(async () => {
  let response = await fetch('https://hcpb.seiwald.club/api/collections/heroes/records?perPage=999&page=1')

  let data = await response.json()

  heroCards.value.push(...data.items)

  response = await fetch('https://hcpb.seiwald.club/api/collections/heroes/records?perPage=999&page=2')

  data = await response.json()

  heroCards.value.push(...data.items)

  hero.value = heroCards.value[counter.value].data
})


</script>

<template>
  <a href="http://127.0.0.1:3333/"><img v-if="hero" src="heroclash-logo-lang.png" alt="heroclash logo" class="Logo"></a>
  

  <H1 v-if="hero" class="Number">
    HERO NR.
  </H1>
  <div class="counter">
    <span @click="counter--" class="firstOne">&lt  </span>{{ '\xa0' }}{{ '\xa0' }} <input v-model="counter">{{ '\xa0' }}{{ '\xa0' }} <span @click="counter++" class="secondOne">></span> </div> 
  
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
    cursor: pointer;
  }
.Number{
  position: absolute;
  top: 12%;
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
.counter{
  display: flex;
  align-items: center;
  justify-content: center;
  position: absolute;
  left: 43%;
  top: 20%;
}
input[type="number"] {
  text-align: center;
  border: none;
 
}
input{
  font-size: 1.75rem;
  width: 200px;
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
.firstOne
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
.secondOne
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

