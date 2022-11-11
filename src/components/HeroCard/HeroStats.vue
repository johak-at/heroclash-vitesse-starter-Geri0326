<script setup>
const props = defineProps(['name', 'stats', 'alignment'])
</script>

<template>
  <div :class="alignment">
    <h1>
      {{ name }}
    </h1>

    <div class="statfield">
      <StatField v-for="(value, key) in stats" :key="key" :skill="key" :value="value">
        <div>
          {{ key }}:{{ value }}
        </div>
      </StatField>
    </div>
  </div>
</template>

<style scoped>
.statfield {
  position: absolute;
width: 165px;
padding-left: 15px;
padding-right: 15px;
margin-bottom: 30px;
text-align: center;
font-size: 17px;
color: black;
font-weight: bold;
}
h1{
  font-size: 21px;
  color: white;
  font-weight: bold;
  text-align: left;
  padding-left: 15px;
}

.bad{
  background-color: red;
}

.good{
  background: linear-gradient(to right, rgb(182, 244, 146), rgb(51, 139, 147));
}
</style>
