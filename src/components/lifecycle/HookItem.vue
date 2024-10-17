<script setup>
import { ref } from 'vue'
import CircleItem from './ComponentItem.vue'

const componentExists = ref(false)
const circleColor = ref('transparent')
const counter = ref(0)

const createCircle = () => {
  componentExists.value = true
  counter.value = 0
}

const deleteCircle = () => {
  componentExists.value = false
  counter.value = 0
}

const updateCircle = () => {
  counter.value++
}

const changeColor = color => {
  circleColor.value = color
}
</script>

<template>
  <div class="container-wrapper">
    <div class="container">
      <span>onMounted</span>
      <div class="circle" style="background-color: blue"></div>
    </div>
    <div class="container">
      <span>onUpdated</span>
      <div class="circle" style="background-color: red"></div>
    </div>
    <div class="container">
      <span>onUnmounted</span>
      <div class="circle" style="background-color: yellow"></div>
    </div>
    <div class="container-2">
      <div class="buttons">
        <button @click="createCircle">Create</button>
        <button @click="deleteCircle">Delete</button>
        <button @click="updateCircle">Update</button>
      </div>
      <div class="circle-placeholder" :style="{ backgroundColor: circleColor }">
        <CircleItem
          v-if="componentExists"
          :count="counter"
          @componentLifecycle="color => changeColor(color)"
        />
      </div>
    </div>
  </div>
</template>

<style>
button {
  margin: 0 1rem;
  cursor: pointer;
}

.container-wrapper {
  position: relative;
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  flex-direction: row;
  margin: 2rem 0;
  border: 1px solid var(--color-border);
}

.container {
  padding: 1rem;
  width: 170px;
  height: 100px;
  margin: 1rem;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-between;
  border: 1px solid var(--color-border);
}

.container-2 {
  padding: 1rem;
  width: 400px;
  margin-bottom: 2rem;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-between;
  border: 1px solid var(--color-border);
}

.buttons {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  flex: 1;
  margin: 1rem 0;
}

.circle {
  margin: 0.2rem;
  width: 20px;
  height: 20px;
  border-radius: 50%;
  border: 1px solid var(--color-border);
}

.circle-placeholder {
  margin: 0.2rem;
  width: 100px;
  height: 100px;
  border-radius: 50%;
  border: 1px solid var(--color-border);
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
