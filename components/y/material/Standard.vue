<template lang="pug">
| YMaterialStandard
div
  YMaterial
</template>

<script setup lang="ts">
import { MeshStandardMaterial } from 'three';

const emit = defineEmits<(e: "value", value: MeshStandardMaterial) => void>();
const material = new MeshStandardMaterial();
emit("value", material)
onUnmounted(() => {
  material.dispose()
})
</script>