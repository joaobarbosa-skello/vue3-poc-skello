<script setup>
import { ref, onMounted, onUpdated, onUnmounted } from 'vue'

const props = defineProps({
  count: Number,
})
const emit = defineEmits(['componentLifecycle'])

const color = ref('transparent')

onMounted(() => {
  color.value = 'blue'
  emit('componentLifecycle', color.value)
})

onUpdated(() => {
  color.value = 'red'
  emit('componentLifecycle', color.value)
})

onUnmounted(() => {
  color.value = 'yellow'
  emit('componentLifecycle', color.value)
})
</script>

<template>
  <div class="placeholder">{{ props.count }}</div>
</template>

<style>
.placeholder {
  color: white;
  font-size: xx-large;
  font-weight: bold;
}
</style>
