<script setup lang="ts">
import { until , invoke } from '@vueuse/core'
import {ref} from 'vue'

const source = ref(0)

invoke(async () => {
  await until(source).toBe(4)
  console.log('满足条件了')
}) 

const clickedFn = () => {
  source.value ++
}
</script>

<template>
 <div>{{source}}</div>
  <button @click="clickedFn">
    点击按钮
  </button>
</template>