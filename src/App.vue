<template>
  <div class="app">
    <h1>Simon's cooles Bizeps Game</h1>
    <button :style="buttonStyle" @mouseover="moveButton">Klick für Bizeps!</button>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';

const buttonStyle = ref({
  top: '50%',
  left: '50%',
  transform: 'translate(-50%, -50%)'
});

const moveButton = () => {
  const randomTop = Math.random() * 90 + 5; // Between 5% and 95%
  const randomLeft = Math.random() * 90 + 5; // Between 5% and 95%
  buttonStyle.value = {
    top: `${randomTop}%`,
    left: `${randomLeft}%`,
    transform: 'translate(-50%, -50%)'
  };
};
</script>

<style scoped>
.app {
  display: flex;

  height: 80vh;
  position: relative;
}

button {
  position: absolute;
  display: flex;
  justify-content: center;
  align-items: center;
  border: 4px solid black;
  font-size: 22px;
  height: 60px;
  width: 290px;
  cursor: pointer;
}
</style>
