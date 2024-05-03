<script setup lang="ts">
// Import the ref function from Vue
import { ref } from 'vue'

// Import the MyList component
import ColorContrast from './components/ColorContrast.vue'
import ColorInput from "./components/ColorInput.vue";

const firstColor = ref('');
const secondColor = ref('');

</script>

<template>
  <div>
    <color-input v-model:fist-color="firstColor" v-model:second-color="secondColor"/>
    <color-contrast :first-color="firstColor" :second-color="secondColor" />

  </div>
</template>
