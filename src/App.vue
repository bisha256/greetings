<template>
  <div style="display: flex; justify-content: space-between">
    <ConfettiExplosion :particleCount="200" :force="0.3" />
    <h1>Sorry you got a cold becuase of me</h1>
    <ConfettiExplosion :particleCount="200" :force="0.3" />
  </div>
</template>

<script setup>
import ConfettiExplosion from "vue-confetti-explosion";
</script>
