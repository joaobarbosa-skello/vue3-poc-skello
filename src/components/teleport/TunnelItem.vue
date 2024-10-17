<script setup>
import { ref } from 'vue'

const open = ref(false)
</script>

<template>
  <div class="container" :style="{ width: '500px', height: '300px' }">
    <div class="container" :style="{ width: '400px', height: '250px' }">
      <div class="container" :style="{ width: '350px', height: '200px' }">
        <div class="container" :style="{ width: '300px', height: '150px' }">
          <div class="container" :style="{ width: '250px', height: '100px' }">
            <div class="container" :style="{ width: '200px', height: '50px' }">
              <div
                @click="open = true"
                class="container clickable"
                :style="{
                  width: '150px',
                  height: '20px',
                  padding: '0px',
                  margin: '0px',
                }"
              ></div>
              <Teleport to="body">
                <div v-if="open" class="modal">
                  <p>Hello from the modal!</p>
                  <button @click="open = false">Close</button>
                </div>
              </Teleport>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.container {
  padding: 1rem;
  margin: 1rem;
  display: flex;
  align-items: center;
  justify-content: center;
  border: 1px solid var(--color-border);
}

.modal {
  position: fixed;
  z-index: 999;
  top: 20%;
  left: 50%;
  width: 300px;
  margin-left: -150px;
  background-color: lightgray;
  border: 2px solid black;
  border-radius: 5px;
  padding: 1rem;
}

.clickable {
  cursor: pointer;
}

.clickable:hover {
  background-color: lightgray;
}
</style>
