<template lang="pug">
YRenderer(@value="renderer = $event")
</template>

<script setup lang="ts">
import type { WebGLRenderer } from 'three';

let renderer: WebGLRenderer;
onMounted(() => {
  document.body.appendChild(renderer.domElement)
})
</script>