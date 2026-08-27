<script setup>
import { ref } from 'vue'
import PropsEmitsChild from './PropsEmitsChild.vue'

const message = ref('초기 메세지')

const handleUpdateRequest = (newMessage) => {
  message.value = newMessage
}
</script>

<template>
  <div class="practice-section">
    <div class="parent-container">
      <h2>Props n Emits</h2>
      <p>
        현재 로컬 데이터(state): <strong>{{ message }}</strong>
      </p>
      <br />
      <PropsEmitsChild :parent-data="message" @update-request="handleUpdateRequest" />
    </div>
  </div>
</template>
