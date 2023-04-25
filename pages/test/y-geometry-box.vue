<template lang="pug">
div
  YGeometryBox(@value="geometry = $event")
</template>

<script setup lang="ts">
import type { BoxGeometry } from 'three';

let geometry: BoxGeometry;
onMounted(() => {
  console.log(geometry)
})
</script>