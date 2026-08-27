<script setup>
import StoreCounter from '@/components/practices/library/StoreCounter.vue'
import AxiosWeather from '@/components/practices/library/AxiosWeather.vue'
import AxiosJson from '@/components/practices/library/AxiosJson.vue'
</script>

<template>
  <div class="practice-container">
    <h1>1. Store</h1>
    <hr />
    <StoreCounter />
    <h1>2. Axios</h1>
    <hr />
    <AxiosWeather />
    <AxiosJson />
  </div>
</template>

<style scoped>
h1 {
  color: #67a1d4;
}
</style>

<style>
@import '@/assets/practice.css';
</style>
