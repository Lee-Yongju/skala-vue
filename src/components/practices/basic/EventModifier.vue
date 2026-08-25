<script setup>
const handleLink = () => {
  alert('링크로 이동하지 않고 함수만 실행됩니다.')
}
const handleBox = () => {
  alert('박스 클릭 이벤트 발생!')
}
const handleChild1 = () => {
  alert('자식1 클릭 이벤트 발생!')
}
const handleChild2 = () => {
  alert('자식2 클릭 이벤트 발생!')
}
</script>

<template>
  <div class="practice-section">
    <h2>이벤트 수식어(Modifiers) 학습</h2>
    <h3>1) .prevent (기본 동작 막기)</h3>
    <a href="https://www.naver.com" @click.prevent="handleLink">네이버로 이동</a>
    <br />

    <h3>2) .stop (이벤트 버블링 막기)</h3>
    <div @click="handleBox">
      <p>박스 클릭</p>
      <button @click="handleChild1">버블링 발생 버튼</button>
      <button @click.stop="handleChild2">버블링 차단 버튼</button>
    </div>
  </div>
</template>
