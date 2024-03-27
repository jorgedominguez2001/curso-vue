<script setup>
import {ref} from 'vue'
let counter =ref(0);
const incremento = () => {
    counter.value ++;
};
const disminucion = () => {
    counter.value --;
};
const resetear = () => {
    counter.value =(0);
};
</script>

<template>
    <h2 :class="counter >= 0 ? 'positive' : 'negative'">
        {{ counter }}
    </h2>
    <button @click="incremento">aumentar</button>
    <button @click="disminucion">disminuir</button>
    <button @click="resetear">resetear</button>
</template>

<style>
h1{
  color: red;
}
.positive{
  color: green;
}
.negative{
  color: red;
}
</style>