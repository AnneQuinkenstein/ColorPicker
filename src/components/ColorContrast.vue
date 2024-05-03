<script setup lang="ts">
interface Props {
  firstColor: string;
  secondColor: string;
}
defineProps<Props>();

const hexToRgb = (hex: string) => {
  const r = parseInt(hex.substring(1, 3), 16);
  const g = parseInt(hex.substring(3, 5), 16);
  const b = parseInt(hex.substring(5, 7), 16);
  return { r, g, b };
}

const normalize = (color: number) => {
  return color <= 0.04045 ? color / 12.92 : Math.pow((color + 0.055) / 1.055, 2.4);
}

const contrast = (color1: string, color2: string) => {
  const rgb1 = hexToRgb(color1);
  const rgb2 = hexToRgb(color2);
  const brightness1 = (normalize(rgb1.r /255) * 0.2126 + normalize(rgb1.g /255) * 0.7152 + normalize(rgb1.b /255)* 0.0722) ;
  const brightness2 = (normalize(rgb2.r /255) * 0.2126 + normalize(rgb2.g /255)* 0.7152 + normalize(rgb2.b /255) * 0.0722) ;
  return Math.abs(brightness1 + 0.05) / (brightness2 + 0.05);
}
</script>

<template>
<p>{{contrast(firstColor, secondColor)}}</p>
</template>

<style scoped>

</style>