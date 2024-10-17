<script setup>
import { computed, reactive, ref } from 'vue'

const count = ref(0)
const computedCount = computed(() => count.value * 2 - state.count)
const state = reactive({
  count: 0,
})
const negativeCount = computed(() => -computedCount.value)

const incrementRef = () => {
  count.value++
}

const decrementRef = () => {
  count.value--
}

const incrementReactive = () => {
  state.count++
}

const decrementReactive = () => {
  state.count--
}
</script>

<template>
  <div class="container-wrapper">
    <div class="container">
      <span
        ><a href="https://vuejs.org/api/reactivity-core.html#ref">Ref</a></span
      >
      <span>{{ count }}</span>
      <div>
        <button @click="decrementRef">-</button>
        <button @click="incrementRef">+</button>
      </div>
    </div>
    <div class="container">
      <span
        ><a href="https://vuejs.org/api/reactivity-core.html#computed"
          >Computed</a
        ></span
      >
      <span>{{ computedCount }}</span>
      <span class="detail">Ref * 2 - Reactive</span>
    </div>
    <div class="container">
      <span
        ><a href="https://vuejs.org/api/reactivity-core.html#reactive"
          >Reactive</a
        ></span
      >
      <span>{{ state.count }}</span>
      <div>
        <button @click="decrementReactive">-</button>
        <button @click="incrementReactive">+</button>
      </div>
    </div>
    <div class="container">
      <span
        ><a href="https://vuejs.org/api/reactivity-core.html#readonly"
          >Read-Only</a
        ></span
      >
      <span>{{ negativeCount }}</span>
      <span class="detail">Negative Computed</span>
    </div>
  </div>
  <span class="subtitle">Extra Materials</span>
  <ul class="list">
    <li>
      <a href="https://vuejsdevelopers.com/2022/06/01/ref-vs-reactive/"
        >Ref VS Reactive</a
      >
    </li>
    <li>
      <a
        href="https://dev.to/adnanbabakan/vue-3-cheat-sheet-of-the-dark-side-part-1-reactivity-5a89#readonly"
      >
        Computed VS Read-Only
      </a>
    </li>
  </ul>
</template>

<style>
button {
  margin: 0 0.5rem;
  cursor: pointer;
}

.container-wrapper {
  position: relative;
  display: flex;
  justify-content: space-around;
  flex-direction: row;
  margin: 2rem 0;
  border: 1px solid var(--color-border);
}

.container {
  padding: 1rem;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-between;
  margin: 1rem 0;
  border: 1px solid var(--color-border);
}

.detail {
  font-size: 0.75rem;
  color: var(--color-text-secondary);
}

.subtitle {
  margin-bottom: 1rem;
}

.list {
  margin: 0.25rem 0;
  font-size: 16px;
}
</style>
