<script setup>
import { ref } from 'vue'

const lazyText = ref('')
const age = ref('')
const userEmail = ref('')
const price = ref('')
</script>

<template>
  <div class="pratice-section">
    <h2>v-model modifier</h2>
    <section style="margin-bottom: 20px">
      <h3>1) lazy modifier</h3>
      <input type="text" v-model.lazy="lazyText" placeholder="입력 후 enter 혹은 외부 클릭" />
      <p>
        실시간이 아니라 확정된 값: <strong>{{ lazyText }}</strong>
      </p>
    </section>

    <section style="margin-bottom: 20px">
      <h3>2) number modifier</h3>
      <input type="text" v-model.number="age" placeholder="나이를 입력하세요" />
      <p>
        입력된 값: <strong>{{ age }}</strong>
      </p>
      <p>
        타입 확인: <strong>{{ typeof age }}</strong>
      </p>
    </section>

    <section style="margin-bottom: 20px">
      <h3>3) trim modifier</h3>
      <input type="text" v-model.trim="userEmail" placeholder="이메일을 입력하세요" />
      <p>
        공백 제거된 값: <strong>{{ userEmail }}</strong>
      </p>
      <p>
        문자열 길이: <strong>{{ userEmail.length }}</strong>
      </p>
    </section>

    <section style="margin-bottom: 20px">
      <h3>4) number + trim modifier</h3>
      <input type="text" v-model.number.trim="price" placeholder="가격을 입력하세요" />
      <p>
        처리된 값: <strong>{{ price }}</strong>
      </p>
      <p>
        타입 확인: <strong>{{ typeof price }}</strong>
      </p>
    </section>
  </div>
</template>
