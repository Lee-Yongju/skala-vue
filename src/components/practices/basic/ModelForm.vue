<script setup>
import { ref } from 'vue'
const comment = ref('')
const isAgreed = ref(false)
const favoriteFruits = ref([])
const gender = ref('')
const selecedCar = ref('')
</script>

<template>
  <div class="practice-section">
    <h2>모든 HTML Form 요소</h2>
    <div>
      <h3>1) Textarea</h3>
      <textarea v-model="comment" placeholder="여기에 입력하세요"></textarea>
      <p>
        데이터 상태: <span>{{ comment }}</span>
      </p>
    </div>
    <div>
      <h3>2) Checkbox</h3>
      <label> <input type="checkbox" v-model="isAgreed" />이용 약관에 동의합니다.</label>
      <p>
        데이터 상태: <span>{{ isAgreed }}</span>
      </p>
    </div>

    <div>
      <h3>3) Checkbox (여러 개)</h3>
      <label><input type="checkbox" value="사과" v-model="favoriteFruits" />사과</label>
      <label><input type="checkbox" value="바나나" v-model="favoriteFruits" />바나나</label>
      <label><input type="checkbox" value="포도" v-model="favoriteFruits" />포도</label>
      <p>
        데이터 상태: <span>{{ favoriteFruits }}</span>
      </p>
    </div>

    <div>
      <h3>4) Radio</h3>
      <label><input type="radio" value="남성" v-model="gender" />남성</label>
      <label><input type="radio" value="여성" v-model="gender" />여성</label>
      <p>
        데이터 상태: <span>{{ gender }}</span>
      </p>
    </div>

    <div>
      <h3>5) Select</h3>
      <select v-model="selecedCar">
        <option disabled value="">차량을 선택하세요</option>
        <option value="hyundai">현대</option>
        <option value="kia">기아</option>
        <option value="ssangyong">쌍용</option>
        <option value="renault">르노삼성</option>
      </select>
      <p>
        데이터 상태: <span>{{ selecedCar }}</span>
      </p>
    </div>
  </div>
</template>
