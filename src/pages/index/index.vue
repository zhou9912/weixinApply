<template>
  <div>
    <p>{{ count }}</p>
    <button @click="increment">watchEffectAAAA</button>
    <button @click="increment">watchPostEffect</button>
    <button @click="increment">watchSyncEffect</button>
  </div>
</template>

<script setup lang="ts">
import { ref, watchEffect, watchPostEffect, watchSyncEffect } from "vue"

const count = ref(0)

const increment = () => {
  count.value++
}

watchEffect(() => {
  console.log(`Count is now ${count.value}`,'watchEffect')
})

watchPostEffect(() => {
  console.log(`Count is now ${count.value}`,'watchPostEffect')
})

watchSyncEffect(() => {
  console.log(`Count is now ${count.value}`,'watchSyncEffect')
})


</script>
