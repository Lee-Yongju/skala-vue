<script setup>
import { ref, watch } from 'vue'

const user = ref({
  name: '홍길동',
  age: 20,
})

const logDeep = ref('아직 감시 시스템이 작동하지 않았습니다')
const logTarget = ref('아직 감시 시스템이 작동하지 않았습니다')

watch(
  user,
  (newVal) => {
    logDeep.value = `[deep 감시] 무언가 변경 됨! 현재 이름: ${newVal.name}, 나이: ${newVal.age}`
  },
  { deep: true },
)

watch(
  () => user.value.age,
  (newAge, oldAge) => {
    logTarget.value = `[target 감시] 나이가 ${oldAge}에서 ${newAge}로 변경되었습니다.`
  },
)
</script>

<template>
  <div class="practice-section">
    <h2>ref 객체/배열 감시</h2>
    <h3>회원 데이터 조작 panel</h3>
    <p>이름: {{ user.name }} / 나이: {{ user.age }}세</p>
    <button @click="user.name = '이순신'">이름만 변경</button>
    <button @click="user.age++">나이만 변경(age++)</button>

    <div class="monitor">
      <p>1) depp: true 모니터(전체 감시)</p>
      <p>{{ logDeep }}</p>
    </div>

    <div class="monitor target">
      <p>2) target 모니터(특정 감시)</p>
      <p>{{ logTarget }}</p>
    </div>
  </div>
</template>
