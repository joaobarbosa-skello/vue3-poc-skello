<script setup>
import { useAttrs } from 'vue'

const props = defineProps({
  title: String,
})
const attrs = useAttrs()
</script>

<template>
  <div class="container">
    <span>{{ props.title }}</span>
    <span>{{ attrs }}</span>
  </div>
</template>

<style>
.container {
  padding: 1rem;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-between;
  margin: 1rem 0;
  border: 1px solid var(--color-border);
}
</style>
