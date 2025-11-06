<script setup>
const emit = defineEmits(['close'])
const props = defineProps({
  message:String
})
</script>

<template>
<div class="wrapper">
  <div class="modal">
<h2>infoモーダル</h2>
<p>{{  message }}</p>
<button @click="emit('close')">閉じる</button>
  </div>
</div>
</template>

<style scoped>

.wrapper{
  background-color: #333;
  position:fixed;
  top:0;
  left:0;
  width:100vw;
  height:100vh;
  display: grid;
  place-items:center;
  
}
.modal{
  background-color: #aaa;
  padding: 20px;
  border-radius: 10px;
}
</style>