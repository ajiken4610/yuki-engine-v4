<template lang="pug">
YScene(@value="scene=$event" v-slot="{p}")
  YCameraPerspective(@value="camera=$event" :p="p")
</template>

<script setup lang="ts">
import type { PerspectiveCamera, Scene } from 'three';

let scene: Scene
let camera: PerspectiveCamera;
onMounted(() => {
  console.log(scene)
})
</script>