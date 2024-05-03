<script setup lang="ts">


const modelFistColor = defineModel('fistColor');
const modelSecondColor = defineModel('secondColor');

const swapColors = () => {
  const temp = modelFistColor.value;
  modelFistColor.value = modelSecondColor.value;
  modelSecondColor.value = temp;
}
</script>

<template>
  <label for="firstColor">First Color</label>
  <input id="firstColor" type="color" v-model="modelFistColor">
  <input type="text" v-model="modelFistColor">


  <label for="secondColor">Second Color</label>
  <input id="secondColor" type="color" v-model="modelSecondColor">
  <input type="text" v-model="modelSecondColor">

  <button type="button" @click="swapColors">Swap Color</button>

</template>

<style scoped>

</style>