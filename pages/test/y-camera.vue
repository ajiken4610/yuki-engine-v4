<template lang="pug">
YScene(@value="scene=$event")
  YCamera(:object="camera")
</template>

<script setup lang="ts">
import { Camera, Scene } from 'three';

let scene: Scene
const camera = new Camera()

</script>