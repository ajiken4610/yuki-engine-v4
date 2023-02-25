<template lang="pug">
YScene(@value="scene = $event")
  YObject3D(:object="o1")
</template>

<script setup lang="ts">
import { Object3D, Scene } from 'three';

let scene: Scene;
const o1 = new Object3D()
onMounted(() => {
  console.log(scene)
})
</script>