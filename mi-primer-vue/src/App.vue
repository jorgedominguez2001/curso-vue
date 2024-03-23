<script setup>
const name = "jorge dominguez";
const stylecolor = "color: blue";
const arraycolores = ["purple","orange","yellow"];
const activo =  true;
</script>

<template>
  <h1 >Hola {{ name }}</h1>
  <h2>{{ arraycolores }}</h2>
  <h2 :style="`color: ${arraycolores[2]}`">soy azul</h2>
</template>
<style>
h1{
  color: red;
}
</style>