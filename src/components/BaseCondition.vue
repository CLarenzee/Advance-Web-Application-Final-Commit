<template>
    <div>
     <input v-model="userInput" placeholder="Type something">
      <p :style="{ color: textColor, fontSize: textSize + 'px' }">{{ userInput }}</p>
      <label for="ChangeColor">Text Color:</label>
      <input id="ChangeColor" type="color" v-model="textColor" />
      <br>
      <label for="fontSizeSlider">Font Size:</label>
      <input id="fontSizeSlider" type="range" min="10" max="100" v-model="textSize" />
      <p>Current Font Size: {{ textSize }}px</p>
    </div>
  
  </template>
  
  <script setup>
  import { ref } from 'vue';
  
  
  const userInput = ref('');
  const textColor = ref('#000000');
  const textSize = ref(16);
  </script>
  