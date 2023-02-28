<template lang="pug">
| YScene
div
  YObject3D(:object="scene" v-bind="props" v-slot="{p:pt}")
    slot(:p="pt")
</template>
<script setup lang="ts">
import { Scene } from 'three';
const props = withDefaults(defineProps<{
  position?: Vec3,
  rotation?: Vec3,
  scale?: Vec3,
  rotationOrder?: RotationOrder,
}>(), {
  position: () => ({ x: 0, y: 0, z: 0 }),
  rotation: () => ({ x: 0, y: 0, z: 0 }),
  scale: () => ({ x: 1, y: 1, z: 1 }),
  rotationOrder: "XYZ"
});

const emit = defineEmits<(e: "value", val: Scene) => void>();

// prepare scene
const scene = new Scene()
emit("value", scene)
</script>