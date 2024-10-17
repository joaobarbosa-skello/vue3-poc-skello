<script setup lang="ts">
import RootItem from './RootItem.vue'
</script>

<template>
  <RootItem title="Root 1" />
  <RootItem v-bind="$attrs" title="Root 2" />
  <RootItem title="Root 3" />
</template>

<style>
.container {
  padding: 1rem;
  display: flex;
  justify-content: space-between;
  margin: 1rem 0;
  border: 1px solid var(--color-border);
}
</style>
