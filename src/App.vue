<script setup>
import ComputedBasic from './compositions/ComputedBasic.vue'
import ReactiveReactive from './compositions/ReactiveReactive.vue'
import ReactiveRef from './compositions/ReactiveRef.vue'
</script>

<template>
  <div style="padding: 20px">
    <ReactiveRef />
    <ReactiveReactive />

    <ComputedBasic />
  </div>
</template>

<style>
@import '@/assets/practice.css';
</style>
