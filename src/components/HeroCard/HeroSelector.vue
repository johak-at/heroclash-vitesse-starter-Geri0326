<script setup>
const emits = defineEmits(['changeHero'])
const counter = ref(1)
function isPositive() {
  if (counter.value !== 1)
    counter.value--
}
</script>

<template>
  <div class="counter">
    <span class="Arrows" @click="isPositive(), emits('changeHero', counter)">&lt;  </span>
    <input id="HeroNumber" v-model="counter" type="number" class="counterInput" min="1" max="600" @input="emits('changeHero', counter)">
    <span class="Arrows" @click="counter++, emits('changeHero', counter)">></span>
  </div>
</template>

<style>
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
.counterInput{
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
