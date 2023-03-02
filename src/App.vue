<template>
  <div style="display: flex; justify-content: space-between">
    <ConfettiExplosion :particleCount="200" :force="0.3" />
    <h1>What a great looking Header this is</h1>
    <ConfettiExplosion :particleCount="200" :force="0.3" />
  </div>
</template>

<script setup>
import ConfettiExplosion from "vue-confetti-explosion";
</script>
