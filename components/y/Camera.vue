<template lang="pug">
| YObject3D
div
  YObject3D(v-bind="props" v-slot="{p:pt}")
    slot(:p="pt")
</template>

<script setup lang="ts">
import type { Camera } from 'three';

const props = withDefaults(defineProps<{
  position?: Vec3,
  rotation?: Vec3,
  scale?: Vec3,
  rotationOrder?: RotationOrder,
  p?: string,
  object: Camera
}>(), {
  position: () => ({ x: 0, y: 0, z: 0 }),
  rotation: () => ({ x: 0, y: 0, z: 0 }),
  scale: () => ({ x: 1, y: 1, z: 1 }),
  rotationOrder: "XYZ"
});
</script>