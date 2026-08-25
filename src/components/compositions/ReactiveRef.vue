<script setup>
import { ref } from 'vue'
const count = ref(0)
const name = ref('홍길동')
const isActive = ref(true)
const items = ref(['사과', '배'])
const user = ref({
  name: '이순신',
  age: 20,
})
const increaseRef = () => {
  count.value++
}
const changeUserName = () => {
  user.value.name = '장보고'
}
</script>

<template>
  <div class="practice-section">
    <h2>반응형 상태 ref() 기초</h2>
    <p>
      Ref Count: <strong>{{ count }}</strong>
    </p>
    <p>이름: <input v-model="name" />{{ name }}</p>
    <p>활성화 여부: {{ isActive ? '활성' : '비활성' }}</p>
    <p>과일 목록: {{ items.join(', ') }}</p>
    <p>사용자 정보: 이름 - {{ user.name }}, 나이 - ({{ user.age }}세)</p>
    <button @click="increaseRef">Ref 증가</button>
    <button @click="isActive = !isActive">활성화 여부 토글</button>
    <button @click="items.push('포도')">과일 추가</button>
    <button @click="changeUserName">사용자 이름 변경</button>
  </div>
</template>
