<script setup>
import { useCounterStore } from '@/stores/counter.js'

const counterStore = useCounterStore()
</script>

<template>
  <div class="practice-section">
    <h2>Counter Store 활용 실습</h2>

    <p>
      원본 카운트 데이터(State): <strong>{{ counterStore.count }}</strong>
    </p>
    <p>
      2배 연산 데이터(getters): <strong>{{ counterStore.doubleCount }}</strong>
    </p>

    <button @click="counterStore.increment">숫자 1 증가(actions)</button>
  </div>
</template>
