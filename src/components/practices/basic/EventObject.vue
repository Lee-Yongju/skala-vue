<script setup>
import { ref } from 'vue'

const position = ref('')
const tagName = ref('')
const getOnlyElement = (e) => {
  position.value = `x: ${e.clientX}, y: ${e.clientY}`
}
const getWithParam = (name, e) => {
  tagName.value = `태그명: ${e.target.tagName}, 이름: ${name}`
}
</script>

<template>
  <div class="practice-section">
    <h2>v-on 이벤트 객체 ($event) 활용</h2>
    <p>좌표: {{ position }}</p>
    <p>태그명: {{ tagName }}</p>
    <button @click="getOnlyElement">클릭 좌표 알아내기</button>
    <button @click="getWithParam('회원A', $event)">회원A 정보 보기</button>
  </div>
</template>
