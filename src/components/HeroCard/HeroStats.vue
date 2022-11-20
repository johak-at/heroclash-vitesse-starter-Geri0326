<script setup>
const props = defineProps(['name', 'stats', 'alignment'])
// if alignment is bad then class is bad if alignment is good then class is good if alignment is neutral then class is neutral
const alignments = computed(() => {
  if (props.alignment === 'bad')
    return 'bad'

  if (props.alignment === 'good')
    return 'good'

  if (props.alignment === 'neutral')
    return 'neutral'
})
</script>

<template>
  <div :class="alignments">
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
text-align: left;
font-size: 14px;
color: black;
font-weight: bold;
border-top-right-radius: 7px;
border-bottom-right-radius: 7px;
}
h1{
  padding-left: 15px;
  padding-top: 5px;
  text-align: left;
  font-weight: 700;
  font-size: 1.25rem;
  line-height: 1.4rem;
  margin: 0;
  padding-bottom: 6px;
}

.bad{
  background: linear-gradient(111.4deg, rgb(246, 4, 26) 0.4%, rgb(251, 139, 34) 100.2%);
    border-top-right-radius: 7px;
    border-bottom-right-radius: 7px;

}

.good{
  background: linear-gradient(to right, rgb(182, 244, 146), rgb(51, 139, 147));
    border-top-right-radius: 7px;
    border-bottom-right-radius: 7px;
}

.neutral{
  background: linear-gradient(111.4deg, rgb(51, 139, 147) 0.4%, rgb(251, 139, 34) 100.2%);
    border-top-right-radius: 7px;
    border-bottom-right-radius: 7px;
}
</style>
