<template lang="pug">
YScene(@value="scene=$event")
  YCameraPerspective(@value="camera=$event")
</template>

<script setup lang="ts">
import type { PerspectiveCamera, Scene } from 'three';

let scene: Scene
let camera: PerspectiveCamera;
onMounted(() => {
  console.log(scene)
})
</script>