<script setup lang="ts">
import { ref, watch } from 'vue'
const props = defineProps({
  count: {
    default: 0,
  },
})
const counter = ref(props.count)
const isRandom = ref(false)
let Interval
watch(isRandom, () => {
  if (isRandom.value) {
    Interval = setInterval(() => {
      counter.value = Math.floor(Math.random() * 35)
    }, 50)
  } else {
    clearInterval(Interval)
    // counter.value = 13
  }
})


</script>

<template>
  <div class="flex">
    <h2>随机抽号：{{ counter }}</h2>
    <button class="ml-5" @click="isRandom = !isRandom">{{ isRandom === false ? '开始' : '暂停' }}</button>
  </div>
</template>