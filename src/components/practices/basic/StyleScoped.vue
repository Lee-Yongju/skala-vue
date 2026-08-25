<script setup></script>

<template>
  <div class="practice-section">
    <h2>Scoped style and external styles</h2>
    <p class="title">Color of this text is red in only this component</p>
    <button class="btn-external">External style button</button>
  </div>
</template>

<style scoped>
.title {
  color: red;
  font-weight: bold;
  font-size: 20px;
}
</style>

<style>
@import '@/assets/practice.css';
</style>
