<template>
  <div style="display: flex; justify-content: space-between">
    <ConfettiExplosion v-if="confetti" :particleCount="200" :force="0.3" />
    <button @click="onClick" class="btn" v-if="!displayMessage">Yay!</button>
    <p v-if="displayMessage" class="paragraph">{{ displayMessage }}</p>
    <ConfettiExplosion v-if="confetti" :particleCount="200" :force="0.3" />
  </div>
</template>

<script setup>
import { ref } from "vue";
import ConfettiExplosion from "vue-confetti-explosion";

const audio = new Audio("/sound/children_yay_sound_effect.mp3");
const confetti = ref(false);
const messages = ["可愛すぎる", "おはよう", "一緒に働くことを楽しんでいます"];

const displayMessage = ref("");

const onClick = () => {
  audio.play();
  confetti.value = true;
  displayMessage.value = messages[Math.floor(Math.random() * messages.length)];
};
</script>

<style>
.btn {
  display: block;
  background-color: #ffc0cb;
  color: white;
  font-size: 1.25rem;
}

.paragraph {
  font-weight: 600;
  font-size: 3rem;
  color: #ffc0cb;
}
</style>
