<template lang="pug">
div
  YMaterialStandard(@value="material = $event")
</template>

<script setup lang="ts">
import type { MeshStandardMaterial } from 'three';

let material: MeshStandardMaterial;
onMounted(() => {
  console.log(material)
})
</script>