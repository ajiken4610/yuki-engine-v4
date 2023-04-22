<template lang="pug">
| YMaterialBasic
div
  YMaterial
</template>

<script setup lang="ts">
import { MeshBasicMaterial } from 'three';

const emit = defineEmits<(e: "value", value: MeshBasicMaterial) => void>();
const material = new MeshBasicMaterial();
emit("value", material)
onUnmounted(() => {
  material.dispose()
})
</script>