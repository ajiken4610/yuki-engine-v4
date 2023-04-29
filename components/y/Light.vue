<template lang="pug">
| YLight
div
  YObject3D(v-bind="props" :object="props.object" v-slot="{p:pt}")
    slot(:p="pt")
</template>

<script setup lang="ts">
import type { Light } from 'three';


const props = withDefaults(defineProps<{
  position?: Vec3,
  rotation?: Vec3,
  scale?: Vec3,
  rotationOrder?: RotationOrder,
  p?: string,
  object: Light
}>(), {
  position: () => ({ x: 0, y: 0, z: 0 }),
  rotation: () => ({ x: 0, y: 0, z: 0 }),
  scale: () => ({ x: 1, y: 1, z: 1 }),
  rotationOrder: "XYZ"
});
const emit = defineEmits<(e: "value", value: Light) => void>()

emit("value", props.object)
</script>