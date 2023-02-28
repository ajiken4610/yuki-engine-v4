<template lang="pug">
| YGroup
div
  YObject3D(v-bind="props" :object="group" v-slot="{p:pt}")
    slot(:p="pt")
</template>

<script setup lang="ts">
import { Group } from 'three';

const props = withDefaults(defineProps<{
  position?: Vec3,
  rotation?: Vec3,
  scale?: Vec3,
  rotationOrder?: RotationOrder,
  p?: string,
}>(), {
  position: () => ({ x: 0, y: 0, z: 0 }),
  rotation: () => ({ x: 0, y: 0, z: 0 }),
  scale: () => ({ x: 1, y: 1, z: 1 }),
  rotationOrder: "XYZ"
});
const emit = defineEmits<(e: "value", value: Group) => void>()

const group = new Group()
emit("value", group)
</script>