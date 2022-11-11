<script setup>
const props = defineProps(['name', 'alignment', 'bio', 'appearance', 'work', 'connections'])
const emits = defineEmits(['hideBiography'])
// get hero name and alignment
const heroName = ref(props.name)
const heroAlignment = ref(props.alignment)
</script>

<template>
  <div id="myModal" class="modal" @click="emits('hideBiography')">
    <!-- Modal content -->
    <div class="modal-content">
      <div class="modal-header">
        <h2>{{ heroName }}</h2>
      </div>
      <div class="modal-body">
        <ul>
          <li v-for="(value, key) in bio" :key="key">
            {{ key }}:{{ '\xa0' }}{{ '\xa0' }}{{ '\xa0' }}{{ value }}
          </li><br>
          <li v-for="(value, key) in appearance" :key="key">
            {{ key }}:{{ '\xa0' }}{{ '\xa0' }}{{ '\xa0' }}{{ value }}
          </li><br>
          <li v-for="(value, key) in work" :key="key">
            {{ key }}:{{ '\xa0' }}{{ '\xa0' }}{{ '\xa0' }}{{ value }}
          </li><br>
          <li v-for="(value, key) in connections" :key="key">
            {{ key }}:{{ '\xa0' }}{{ '\xa0' }}{{ '\xa0' }}{{ value }}
          </li>
        </ul>
      </div>
      <div class="modal-footer">
        <h3>Alignment: {{ heroAlignment }}</h3>
      </div>
    </div>
  </div>
</template>

<style scoped>
.modal-content {
  margin: auto;
  padding: 0;
  position: relative;
  width: 650px;
  background-color: #2b2929;
  text-align: left;
  -webkit-animation-name: animatetop;
  -webkit-animation-duration: 0.4s;
  animation-name: animatetop;
  animation-duration: 0.5s

}

/* Add Animation */
@-webkit-keyframes animatetop {
  from {top:-300px; opacity:0}
  to {top:0; opacity:1}
}
@keyframes animatetop {
  from {top:-300px; opacity:0}
  to {top:0; opacity:1}
}

.modal-body {
  color: white;
  font-size: 13px;
  padding-top: 10px;
  padding-left: 8px;
}
.modal {
  position: fixed;
  z-index: 1;
  padding-top: 40px;
  left: 0;
  top: 0;
  width: 100%; /* Full width */
  height: 100%; /* Full height */
  overflow: auto; /* Enable scroll if needed */
  background-color: rgb(0,0,0); /* Fallback color */
  background-color: rgba(0,0,0,0.4); /* Black w/ opacity */
}

.modal-header {
  padding-left: 8px;
  padding-top: 5px;
  padding-bottom: 5px;
  border-top-left-radius: 3px;
  border-top-right-radius: 3px;
  border-bottom-left-radius: 0px;
  border-bottom-right-radius: 0px;
  background: linear-gradient(to right, rgb(182, 244, 146), rgb(51, 139, 147));
  color: white;
  font-weight: bold;
  font-size: 20px;
}

.modal-footer {
  padding-left: 8px;
  padding-top: 6px;
  padding-bottom: 6px;
  border-bottom-left-radius: 3px;
  border-bottom-right-radius: 3px;
  border-top-left-radius: 0px;
  border-top-right-radius: 0px;
  background: linear-gradient(to right, rgb(182, 244, 146), rgb(51, 139, 147));
  color: white;
}
</style>
