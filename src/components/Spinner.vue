<template>
    <div class="preloader">
      <div class="bouncing-text">
        <span v-for="(letter, index) in letters" :key="index" :style="{ animationDelay: `${index * 0.1}s` }">
          {{ letter }}
        </span>
      </div>
    </div>
  </template>
  
  <script setup>
  const letters = ['T', 'A', 'P', 'I', 'W', 'A'];
  </script>
  
  <style scoped>
  .preloader {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: #fff;
    display: flex;
    align-items: center;
    justify-content: center;
    z-index: 9999;
  }
  
  .bouncing-text {
    font-size: 48px;
    font-weight: bold;
    letter-spacing: 10px;
    display: flex;
  }
  
  .bouncing-text span {
    display: inline-block;
    animation: bounce 1s infinite;
  }
  
  @keyframes bounce {
    0%, 20%, 50%, 80%, 100% {
      transform: translateY(0);
    }
    40% {
      transform: translateY(-30px);
    }
    60% {
      transform: translateY(-15px);
    }
  }
  </style>
  