<script setup>
const hero = ref({
  appearance: {
    eyeColor: 'Yellow',
    gender: 'Male',
    hairColor: 'No Hair',
    height: [
      '6\'8',
      '203 cm',
    ],
    race: 'Human',
    weight: [
      '980 lb',
      '441 kg',
    ],
  },
  biography: {
    aliases: [
      'Rick Jones',
    ],
    alignment: 'good',
    alterEgos: 'No alter egos found.',
    firstAppearance: 'Hulk Vol 2 #2 (April, 2008) (as A-Bomb)',
    fullName: 'Richard Milhouse Jones',
    placeOfBirth: 'Scarsdale, Arizona',
    publisher: 'Marvel Comics',
  },
  connections: {
    groupAffiliation: 'Hulk Family; Excelsior (sponsor), Avengers (honorary member); formerly partner of the Hulk, Captain America and Captain Marvel; Teen Brigade; ally of Rom',
    relatives: 'Marlo Chandler-Jones (wife); Polly (aunt); Mrs. Chandler (mother-in-law); Keith Chandler, Ray Chandler, three unidentified others (brothers-in-law); unidentified father (deceased); Jackie Shorr (alleged mother; unconfirmed)',
  },
  id: 1,
  images: {
    lg: 'images/lg/1-a-bomb.jpg',
    md: 'images/md/1-a-bomb.jpg',
    sm: 'images/sm/1-a-bomb.jpg',
    xs: 'images/xs/1-a-bomb.jpg',
  },
  name: 'A-Bomb',
  powerstats: {
    combat: 64,
    durability: 80,
    intelligence: 38,
    power: 24,
    speed: 17,
    strength: 100,
  },
  slug: '1-a-bomb',
  work: {
    base: '-',
    occupation: 'Musician, adventurer, author; formerly talk show host',
  },
})
</script>

<template>
  <img src="heroclash-logo-lang.png" alt="heroclash logo" class="Logo">
  <H1 class="Number">
    HERO NR.
  </H1>
  <HeroCard :hero="hero" />
</template>

<style>
.Logo{
  position: absolute;
  margin-top: -100px;
  width: 300px;
  left: 40%;
  max-width: 100%;
    height: auto;
    margin-top: 0px;
  }
.Number{
  position: fixed;
  top: 15%;
  left: 44%;
  font-family: "action-comics-black";
  font-size: 1.4rem;
  filter: drop-shadow(2px 2px 2px);
    -webkit-text-stroke: 1px #000;
    background: linear-gradient(45deg, #f7a823, #e4003a);
    -webkit-text-fill-color: transparent;
    -webkit-background-clip: text;
    text-transform: uppercase;
    transition: all 0.1s ease-in-out;
}
</style>

