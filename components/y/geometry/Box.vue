<template lang="pug">
| YGeometryBox
div
  YGeometry
</template>

<script setup lang="ts">
import { BoxGeometry } from 'three';

const emit = defineEmits<(e: "value", value: BoxGeometry) => void>();
const material = new BoxGeometry();
emit("value", material)
onUnmounted(() => {
  material.dispose()
})
</script>