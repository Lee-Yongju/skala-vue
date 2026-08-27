<script setup>
import { ref, onMounted, onUpdated, onUnmounted } from 'vue'

const count = ref(0)
let timerId = null

console.log('1. [setup] Create component instance at memory')

onMounted(() => {
  console.log('2. [onMounted] Component mounted to DOM')

  timerId = setInterval(() => {
    count.value++
  }, 5000)
})

onUpdated(() => {
  console.log(`3. [onUpdated] Component updated (count: ${count.value})`)
})

onUnmounted(() => {
  clearInterval(timerId)
  console.log('4. [onUnmounted] Component unmounted from DOM')
})
</script>

<template>
  <div class="practice-section">
    <h3>⏱️ 라이프사이클 훅 흐름 탐색기</h3>
    <div class="counter-display">
      <p>실시간 타이머 카운트: {{ count }}</p>
      <button @click="count++">수동으로 숫자 올리기</button>
    </div>
  </div>
</template>

<style scoped>
.counter-display {
  background: #e3fafc;
  padding: 15px;
  border-radius: 8px;
  border: 1px solid #99e9f2;
  text-align: center;
}
</style>
