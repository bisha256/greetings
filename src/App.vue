<template>
  <div style="display: flex; justify-content: space-between">
    <ConfettiExplosion :particleCount="200" :force="0.3" />
    <h1>Sorry you caught cold because of me</h1>
    <ConfettiExplosion :particleCount="200" :force="0.3" />
  </div>
</template>

<script setup>
import { onMounted } from "vue";
import ConfettiExplosion from "vue-confetti-explosion";

const audio = new Audio("/sound/children_yay_sound_effect.mp3");

onMounted(async () => {
  await audio.play();
});
</script>
