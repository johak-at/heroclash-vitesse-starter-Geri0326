<script  setup>
const props = defineProps(['skill', 'value'])
</script>

<template>
  <div flex justify-between>
    <span>{{ skill }}</span>
    <span>{{ value }}</span>
  </div>
</template>

<style>
div{
  border-bottom-right-radius: 7px;
  border-top-right-radius: 7px;
  display: block;
    color: white;
    font-family: "DM Sans",ui-sans-serif;
    }
</style>
