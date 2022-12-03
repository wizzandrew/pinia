<template>
  <div class="about">
    <h1>About</h1>
    <div class="count-btn">
      <button @click="storeCounter.increaseCount">
        {{ storeCounter.count }}
      </button>
    </div>
  </div>
</template>

<script setup>
import { useCounterStore } from "../stores/counter";
const storeCounter = useCounterStore();
</script>

<style>
.count-btn button {
  font-size: 40px;
  margin: 10px;
}
</style>
