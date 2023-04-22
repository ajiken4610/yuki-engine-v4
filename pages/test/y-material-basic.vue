<template lang="pug">
div
  YMaterialBasic(@value="material = $event")
</template>

<script setup lang="ts">
import type { MeshBasicMaterial } from 'three';

let material: MeshBasicMaterial;
onMounted(() => {
  console.log(material)
})
</script>