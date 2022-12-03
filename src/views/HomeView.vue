<template>
  <div class="home">
    <div class="count">{{ storeCounter.count }}</div>
    <div class="count-btn">
      <button @click="storeCounter.decreaseCount">-</button>
      <button @click="storeCounter.increaseCount">+</button>
    </div>
    <hr />
    <div>This counter is: {{ oddOrEven }}</div>
  </div>
</template>

<script>
import { computed, defineComponent, ref } from "vue";
import { useCounterStore } from "../stores/counter";

export default defineComponent({
  setup() {
    //pinia state
    const storeCounter = useCounterStore();

    const count = ref(0);

    //computed
    const oddOrEven = computed(() => {
      const remain = count.value % 2;
      return remain === 1 ? "odd" : "even";
    });

    //methods
    const increaseCount = () => {
      count.value += 1;
    };

    const decreaseCount = () => {
      count.value -= 1;
    };

    return { storeCounter, count, oddOrEven, increaseCount, decreaseCount };
  },
});
</script>

<style>
.count {
  font-size: 60px;
  margin: 20px;
}

.count-btn button {
  font-size: 40px;
  margin: 10px;
}
</style>
