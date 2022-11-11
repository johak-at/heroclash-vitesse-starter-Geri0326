<script setup>
const props = defineProps(['name', 'alignment'])
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
        <p>Some text in the Modal Body</p>
        <p>Some other text...</p>
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

}
.modal-body {padding: 2px 16px;}
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
  padding: 2px 16px;
  border-top-left-radius: 3px;
  border-top-right-radius: 3px;
  border-bottom-left-radius: 0px;
  border-bottom-right-radius: 0px;
  background: linear-gradient(to right, rgb(182, 244, 146), rgb(51, 139, 147));
  color: white;
}

.modal-footer {
  padding: 2px 16px;
  border-bottom-left-radius: 3px;
  border-bottom-right-radius: 3px;
  border-top-left-radius: 0px;
  border-top-right-radius: 0px;
  background: linear-gradient(to right, rgb(182, 244, 146), rgb(51, 139, 147));
  color: white;
}
</style>
