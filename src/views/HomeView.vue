<template>
  <div class="home">
    <div class="count">{{ count }}</div>
    <div class="count-btn">
      <button @click="decreaseCount">-</button>
      <button @click="increaseCount">+</button>
    </div>
    <hr />
    <div>This counter is: {{ oddOrEven }}</div>
  </div>
</template>

<script>
import { computed, defineComponent, ref } from "vue";

export default defineComponent({
  setup() {
    const count = ref(0);

    const oddOrEven = computed(() => {
      const remain = count.value % 2;
      return remain === 1 ? "odd" : "even";
    });

    const increaseCount = () => {
      count.value += 1;
    };

    const decreaseCount = () => {
      count.value -= 1;
    };

    return { count, oddOrEven, increaseCount, decreaseCount };
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
