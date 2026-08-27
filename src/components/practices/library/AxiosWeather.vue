<script setup>
import { ref } from 'vue'
import axios from 'axios'

const weatherData = ref(null)
const isLoading = ref(false)

const handleFetchWeather = async () => {
  isLoading.value = true

  const API_KEY = '44aa0f3c63b7bd0d6d524e3563f9ee6c'
  const URL = `https://api.openweathermap.org/data/2.5/weather?q=Seoul&appid=${API_KEY}&units=metric&lang=krl`

  try {
    const response = await axios.get(URL)

    console.log('Axios 통신 응답 전체 객쳬: ', response)
    console.log('Axios 통신 응답 데이터(JSON): ', response.data)
    weatherData.value = response.data
  } catch (error) {
    console.error('통신 중 에러 발생', error)
    alert('데이터를 가져오지 못했습니다. API KEY와 URL을 확인해주세요.')
  } finally {
    isLoading.value = false
  }
}
</script>

<template>
  <div class="practice-section">
    <h2>Axios 통신 검증</h2>
    <button @click="handleFetchWeather" :disabled="isLoading">
      {{ isLoading ? '데이터 로딩 중...' : '실시간 날씨 데이터 가져오기' }}
    </button>

    <div v-if="weatherData" class="result-card">
      <p>
        위치: <strong>{{ weatherData.name }}</strong>
      </p>
      <p>
        현재 기온: <strong>{{ weatherData.main.temp }}°C</strong>
      </p>
      <p>
        날씨 상태: <strong>{{ weatherData.weather[0].description }}</strong>
      </p>
      <p>
        습도: <strong>{{ weatherData.main.humidity }}%</strong>
      </p>
    </div>
    <div v-else>
      <p>데이터가 없습니다. 버튼을 눌러 날씨 데이터를 가져오세요.</p>
    </div>
  </div>
</template>

<style scoped>
.result-card {
  background: #f8fafc;
  padding: 15px;
  border-radius: 8px;
  border: 1px solid #e2e8f0;
  line-height: 1.8;
}
.result-card strong {
  color: #0284c7;
}
</style>
