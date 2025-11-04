<script setup>
const emit = defineEmits(['close'])
const props = defineProps({
  title:String
})
</script>

<template>
  <div class="wrapper" @click.self="emit('close')">
    <div class="modal">
      <h2>{{ title }}</h2>
    <p>モーダルウィンドウのコンポーネントです！</p>
     <button @click="emit('close')">モーダルを閉じる</button>
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