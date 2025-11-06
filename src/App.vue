<script setup>
import { ref } from 'vue'
import ModalWindow from './ModalWindow.vue'
import InfoModal from './InfoModal.vue'

const isModalOpen = ref(false) 
const infoModalOpen =ref(false)
</script>

<template>
 <div>
 <h1>モーダル練習アプリ</h1>
 <button @click="isModalOpen = true">モーダルを開く</button>
 <button @click="infoModalOpen = true">infoモーダルを開く</button>
<transition name="scale">
 <ModalWindow v-if="isModalOpen" @close="isModalOpen = false" title="注意!">
  <template #title >
  </template>
<p>本当に削除しますか？</p>
<button>はい</button>
<button>いいえ</button>
 </ModalWindow>
</transition>
<InfoModal v-if="infoModalOpen" @close="infoModalOpen = false" />

 </div>
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
.overlay{
  position:fixed;
  inset:0;
  display:grid;
  place-items:center;
}

.scale-enter-active,.scale-leave-active{
  transform:scale(1);
  opacity:1;
transition:all 0.3s ease-in-out;
}
.scale-enter-to,.scale-leave-from{
}
.scale-enter-from,.scale-leave-to{
  transform:scale(0.8);
  opacity:0;
transition :all 1s ease-in-out;
}
</style>
