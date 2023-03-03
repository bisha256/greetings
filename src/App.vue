<template>
  <div style="display: flex; justify-content: space-between">
    <ConfettiExplosion v-if="confetti" :particleCount="200" :force="0.3" />
    <button @click="onClick" class="btn">Yay!</button>
    <ConfettiExplosion v-if="confetti" :particleCount="200" :force="0.3" />
  </div>
</template>

<script setup>
import { ref } from "vue";
import ConfettiExplosion from "vue-confetti-explosion";

const audio = new Audio("/sound/children_yay_sound_effect.mp3");
const confetti = ref(false);

const onClick = () => {
  audio.play();
  confetti.value = true;
};
</script>

<style>
.btn {
  display: block;
  background-color: #ffc0cb;
  color: white;
}
</style>
