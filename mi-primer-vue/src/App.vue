<template>
  <h2 :class="classCounter">
    {{ counter }}
  </h2>
  <button @click="incremento">aumentar</button>
  <button @click="disminucion">disminuir</button>
  <button @click="resetear">resetear</button>
  <button @click="añadir" :disabled="blockNumber">Add</button>
  <ul>
    <li v-for="(numero, index) in array" :key="index">{{ numero }}</li>
  </ul>
</template>

<script setup>
import { ref, computed } from 'vue';

let counter = ref(0);
let array = ref([]);

const incremento = () => {
  counter.value++;
};

const disminucion = () => {
  counter.value--;
};

const resetear = () => {
  counter.value = 0;
};

const añadir = () => {
  const numsearch = array.value.find(numero => numero === counter.value);
  if (numsearch === undefined) {
    array.value.push(counter.value);
  }
};

const classCounter = computed(() => {
  if (counter.value === 0) {
    return "zero";
  } else if (counter.value > 0) {
    return "positive";
  } else {
    return "negative";
  }
});

const blockNumber = computed(() => {
  return array.value.includes(counter.value);
});
</script>

<style>
.positive {
  color: green;
}
.negative {
  color: red;
}
.zero {
  color: blueviolet;
}
</style>
