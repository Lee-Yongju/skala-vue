<script setup>
import ComputedBasic from './components/compositions/ComputedBasic.vue'
import ReactiveReactive from './components/compositions/ReactiveReactive.vue'
import ReactiveRef from './components/compositions/ReactiveRef.vue'
import WatchersBasic from './components/compositions/WatchersBasic.vue'
import WatchersMulti from './components/compositions/WatchersMulti.vue'
import WatchersDeep from './components/compositions/WatchersDeep.vue'
import WatchersReactive from './components/compositions/WatchersReactive.vue'
import WatchersWatchEffect from './components/compositions/WatchersWatchEffect.vue'
import WatchersRefArray from './components/compositions/WatchersRefArray.vue'
import WatchersReactiveArray from './components/compositions/WatchersReactiveArray.vue'
</script>

<template>
  <div style="padding: 20px">
    <ReactiveRef />
    <ReactiveReactive />

    <ComputedBasic />

    <hr />

    <WatchersBasic />
    <WatchersMulti />
    <WatchersDeep />
    <WatchersReactive />
    <WatchersWatchEffect />
    <WatchersRefArray />
    <WatchersReactiveArray />
  </div>
</template>

<style>
@import '@/assets/practice.css';
</style>
